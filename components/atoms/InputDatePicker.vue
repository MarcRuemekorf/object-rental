<template>
  <component :is="htmlTag">
    <label
      v-if="label"
      :for="name"
      class="block mb-1 text-sm"
    >
      {{ label }} <span v-if="required" class="text-red-600">*</span>
    </label>
    <vue-pikaday
      v-model="inputValue"
      :id="name"
      placeholder="Pick a date"
      :options="options"
      :class="['w-full sm:text-sm border-gray-200 shadow-sm rounded border border-gray-300', errors.length ? 'border-red-500 text-red-600 focus:ring-red-500 focus:border-red-500 placeholder-red-400' : 'focus:ring-blue-500 focus:border-blue-500 placeholder-gray-400']"
    />
    <!-- Helper text -->
    <div v-if="helper" class="text-sm text-gray-400">
      {{ helper }}
    </div>
    <!-- Error text -->
    <ul v-if="errors.length" class="text-sm text-red-500">
      <li v-for="(error, index) in errors" :key="index">
        {{ error }}
      </li>
    </ul>
  </component>
</template>
<script>
import {ref, watch} from '@nuxtjs/composition-api'
export default {
  name: 'InputDatePicker',
  props: {
    htmlTag: {
      type: String,
      default: 'div'
    },
    value: {
      type: Date,
      default: ''
    },
    name: {
      type: String,
      default: ''
    },
    label: {
      type: String,
      default: ''
    },
    placeholder: {
      type: String,
      default: ''
    },
    required: {
      type: Boolean,
      default: false
    },
    helper: {
      type: String,
      default: ''
    },
    errors: {
      type: Array,
      default: () => []
    },
    options: {
      type: Object,
      default: () => {}
    }
  },
  setup(props) {
    const inputValue = ref(props.value)

    watch(
      () => props.value,
      (value) => {
        inputValue.value = value
      }
    )

    return {
      inputValue
    }
  }
}
</script>
