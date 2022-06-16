<template>
  <div class="relative h-screen flex justify-center items-center bg-gray-100">

    <div class="bg-white shadow overflow-hidden sm:rounded-md w-72">
      <ul role="list" class="divide-y divide-gray-200">
        <li>
          <nuxt-link to="/form-picker" class="flex justify-between items-center px-4 py-4 sm:px-6 hover:bg-gray-50">
            <div>
              <span class="block text-xs text-gray-400">Opdracht 1</span>
              Form Picker
            </div>
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M13 7l5 5m0 0l-5 5m5-5H6" />
            </svg>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="/webdesign" class="flex justify-between items-center px-4 py-4 sm:px-6 hover:bg-gray-50">
            <div>
              <span class="block text-xs text-gray-400">Opdracht 2</span>
              Webdesign
            </div>
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M13 7l5 5m0 0l-5 5m5-5H6" />
            </svg>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="/case" class="flex justify-between items-center px-4 py-4 sm:px-6 hover:bg-gray-50">
            <div>
              <span class="block text-xs text-gray-400">Opdracht 3</span>
              Case
            </div>
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M13 7l5 5m0 0l-5 5m5-5H6" />
            </svg>
          </nuxt-link>
        </li>
        <li class="px-4 py-4 sm:px-6 bg-gray-50">
          <nuxt-link to="/bonus" class="flex justify-between items-center">
            <div>
              Bonus
            </div>
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M13 7l5 5m0 0l-5 5m5-5H6" />
            </svg>
          </nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import InputDatePicker from "@/components/atoms/InputDatePicker";
import InputText from "@/components/atoms/InputText";
import Button from "@/components/atoms/Button";
import { ref } from '@nuxtjs/composition-api';
import moment from 'moment';
export default {
  name: 'IndexPage',
  components: {
    InputDatePicker,
    InputText,
    Button
  },
  setup() {
    const name = ref('')
    const now = ref(new Date())
    const startDate = ref(now.value)
    const endDate = ref(null)
    const startDateOptions = ref({
      format: 'YYYY/MM/DD',
      minDate: moment().toDate(),
      maxDate: moment().add(7, 'days').toDate()
    })
    const endDateOptions = ref({
      format: 'YYYY/MM/DD',
      minDate: moment(new Date(startDate.value)).add(1, 'days').toDate(),
      maxDate: moment(new Date(startDate.value)).add(7, 'days').toDate()
    })

    return {
      name,
      startDate,
      endDate,
      startDateOptions,
      endDateOptions
    }
  }
}
</script>
