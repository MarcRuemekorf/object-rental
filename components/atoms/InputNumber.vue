<template>
  <component :is="htmlTag">
    <label
      v-if="label"
      :for="name"
      class="block mb-1 text-sm"
    >
      {{ label }} <span v-if="required" class="text-red-600">*</span>
    </label>
    <div class="relative">
      <div v-if="prepend" class="absolute top-0 left-0 bottom-0 max-h-full text-sm flex items-center justify-center ml-3">
        {{ prepend }}
      </div>

      <input
        :id="name"
        v-model="inputValue"
        type="number"
        :name="name"
        :placeholder="placeholder"
        :min="min"
        :max="max"
        :step="step"
        :class="['w-full sm:text-sm shadow-sm rounded border border-gray-300', errors.length ? 'border-red-500 text-red-600 focus:ring-red-500 focus:border-red-500 placeholder-red-400' : 'focus:ring-gray-500 focus:border-gray-500 placeholder-gray-400', prepend ? 'pl-6' : 'pl-3', append ? 'pr-9' : !controls ? 'pr-3' : 'pr-6']"
        @input="$emit('input', inputValue)"
      >

      <div v-if="append" class="absolute top-0 right-6 bottom-0 max-h-full">
        {{ append }}
      </div>

      <div v-if="controls" class="absolute top-0 right-0 bottom-0 w-6 max-h-full flex flex-col divide-y border-l">
        <button type="button" class="flex flex-1 w-full items-center justify-center text-gray-400 hover:text-gray-500" @click="increment">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M14.707 12.707a1 1 0 01-1.414 0L10 9.414l-3.293 3.293a1 1 0 01-1.414-1.414l4-4a1 1 0 011.414 0l4 4a1 1 0 010 1.414z" clip-rule="evenodd" />
          </svg>
        </button>
        <button type="button" class="flex flex-1 w-full items-center justify-center text-gray-400 hover:text-gray-500" @click="decrement">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
          </svg>
        </button>
      </div>
    </div>

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
import { ref, watch } from '@nuxtjs/composition-api'
export default {
  name: 'InputNumber',

  props: {
    htmlTag: {
      type: String,
      default: 'div'
    },
    value: {
      type: [String, Number],
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
    controls: {
      type: Boolean,
      default: true
    },
    prepend: {
      type: String,
      default: ''
    },
    append: {
      type: String,
      default: ''
    },
    placeholder: {
      type: String,
      default: ''
    },
    min: {
      type: Number,
      default: null
    },
    max: {
      type: Number,
      default: null
    },
    step: {
      type: Number,
      default: 1
    },
    helper: {
      type: String,
      default: ''
    },
    errors: {
      type: Array,
      default: () => []
    },
    required: {
      type: Boolean,
      default: false
    }
  },
  emits: [
    'input',
    'blur'
  ],
  setup (props, { emit }) {
    const inputValue = ref(props.value)

    const increment = () => {
      if (inputValue.value === props.max) {
        return
      }
      inputValue.value++

      emit('input', inputValue.value)
      emit('change')
    }

    const decrement = () => {
      if (inputValue.value === props.min) {
        return
      }
      inputValue.value--

      emit('input', inputValue.value)
      emit('change')
    }

    watch(
      () => props.value,
      (value) => {
        inputValue.value = value
      }
    )

    return {
      inputValue,
      increment,
      decrement
    }
  }

}
</script>

<style>
input[type='number']::-webkit-inner-spin-button,
input[type='number']::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type=number] {
  -moz-appearance: textfield;
}
</style>
