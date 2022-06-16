<template>
  <div class="bg-gray-100 min-h-screen flex flex-col justify-center py-12 sm:px-6 lg:px-8">
    <div class="fixed top-6 left-6">
      <nuxt-link to="/" class="flex items-center space-x-2 px-3 py-2 bg-white shadow-lg rounded text-gray-400 hover:text-gray-900">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M11 17l-5-5m0 0l5-5m-5 5h12" />
        </svg>
        Terug
      </nuxt-link>
    </div>
    <div class="sm:mx-auto sm:w-full sm:max-w-md text-center">
      <span class="block text-sm text-gray-400">Opdracht 1</span>
      <h2 class=" text-center text-3xl font-extrabold text-gray-900">Form Picker</h2>
    </div>

    <div class="mt-8 sm:mx-auto sm:w-full sm:max-w-md">
      <div class="bg-white py-8 px-4 shadow sm:rounded-lg sm:px-10">
        <form class="space-y-12" action="#" method="POST">

          <div class="grid grid-cols-2 gap-3">
            <div class="sm:col-span-2">
              <InputSelect
                v-model="developers.selected"
                name="select-object"
                label="Select ontwikkelaar"
                helper="Selecteer een ontwikkelaar"
                :options="developers.options"
                searchable
                :errors="formErrors.developerId"
              />
            </div>

            <div class="sm:col-span-1">
              <InputDatePicker
                v-model="startDate.selected"
                name="start-date"
                label="Start datum"
                :options="startDate.options"
                :errors="formErrors.startDate"
                @blur="validate('startDate')"
              />
            </div>

            <div class="sm:col-span-1">
              <InputDatePicker
                v-model="endDate.selected"
                name="end-date"
                label="Eind datum"
                :options="endDate.options"
                :errors="formErrors.endDate"
                @blur="validate('endDate')"
              />
            </div>
          </div>
          {{ formErrors }}

          <div>
            <Button size="lg" class="w-full" @click="checkAvailability">Check availability</Button>

            <div v-if="message.text" :class="['mt-6 flex items-center text-sm', message.type === 'error' ? 'text-red-600' : 'text-green-600']">
              <svg v-if="message.type === 'error'" xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7 4a1 1 0 11-2 0 1 1 0 012 0zm-1-9a1 1 0 00-1 1v4a1 1 0 102 0V6a1 1 0 00-1-1z" clip-rule="evenodd" />
              </svg>
              <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              {{ message.text }}
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
import InputSelect from "@/components/atoms/InputSelect";
import InputDatePicker from "@/components/atoms/InputDatePicker";
import InputText from "@/components/atoms/InputText";
import Button from "@/components/atoms/Button";
import { ref, onMounted } from '@nuxtjs/composition-api';
import { object, number, string } from 'yup';
import moment from "moment";

const checkAvailabilityForm = object().shape({
  developerId: number().nullable(true).required('Selecteer alsjeblieft een ontwikkelaar'),
  startDate: string().nullable(true).required('Een startdatum is verplicht'),
  endDate: string().nullable(true).required('Een einddatum is verplicht'),
})

export default {
  name: 'FormPickerPage',
  components: {
    InputSelect,
    InputDatePicker,
    InputText,
    Button
  },
  setup() {
    const message = ref({
      type: '',
      text: ''
    })
    const developers = ref({
      status: 'LOADING',
      selected: {},
      options: []
    })
    const now = ref(new Date())
    const startDate = ref({
      selected: now,
      options: {
        format: 'YYYY/MM/DD',
        minDate: moment().toDate(),
        maxDate: moment().add(1, 'years').toDate()
      }
    })
    const endDate = ref({
      selected: null,
      options: {
        format: 'YYYY/MM/DD',
        minDate: moment(new Date(startDate.value.selected)).add(1, 'days').toDate(),
        maxDate: moment(new Date(startDate.value.selected)).add(1, 'years').toDate()
      }
    })
    const formData = ref({
      developerId: null,
      startDate: null,
      endDate: null
    })
    const formErrors = ref({
      developerId: [],
      startDate: [],
      endDate: []
    })
    const getDevelopers = async () => {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/users')
        const data = await response.json();

        if(!data) {
          developers.value.status = 'ERROR'
        } else if(data.length < 1) {
          developers.value.status = 'EMPTY'
        } else {
          const arr = []
          Object.keys(data).forEach((key) => {
            arr.push({
              value: data[key].id,
              label: data[key].name,
              description: data[key].email
            })
          })
          developers.value.options = arr

          developers.value.status = 'OK'
        }

      } catch {
        message.value = 'Oops er is iets fout gegaan bij het ophalen van ontwikkelaars'
      }
    }

    onMounted(() => {
      getDevelopers()
    })

    const validate = async (field) => {

      try {
        await checkAvailabilityForm.validateAt(field, formData.value)
        formErrors.value[field] = []
      } catch (err) {
        formErrors.value[field].push(err.message)
      }
    }

    const validateForm = async () => {
      console.log('validating form')
      const fields = [
        'developerId',
        'startDate',
        'endDate'
      ]

      for (const field of fields) {
        await validate(field)
      }

      for (const property in formErrors.value) {
        if (formErrors.value[property] !== '') { return false }
      }
      return true
    }

    const checkAvailability = async () => {
      // Reset errors
      formErrors.value = {
        developerId: [],
        startDate: [],
        endDate: []
      }

      // Prepare data
      if(developers.value.selected.value) {
        formData.value.developerId = developers.value.selected.value
      }

      if(startDate.value.selected) {
        formData.value.startDate = startDate.value.selected
      }

      if(endDate.value.selected) {
        formData.value.endDate = endDate.value.selected
      }

      const isValid = await validateForm();
      if(isValid) {
        console.log(formData)
        try {
          await fetch(url, {
            method: 'POST',
            headers: {
              'Content-Type': 'application/json'
            },
            body: JSON.stringify(formData)
          });

          // Skipping response

          message.value = {
            type: 'success',
            text: 'Er is iets fout gegaan probeer het opnieuw'
          }

        } catch {
          message.value = {
            type: 'error',
            text: 'Er is iets fout gegaan probeer het opnieuw'
          }
        }
      } else {
        message.value = {
          type: 'error',
          text: 'The form contains errors'
        }
      }
    }

    return {
      message,
      developers,
      startDate,
      endDate,
      formErrors,
      validate,
      checkAvailability
    }
  }
}
</script>
