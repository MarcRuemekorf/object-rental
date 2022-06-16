<template>
  <div>
    <label
      v-if="label"
      :for="name"
      class="block mb-1 text-sm"
    >
      {{ label }} <span v-if="required" class="text-red-600">*</span>
    </label>
    <div :class="['relative']">
      <input
        v-if="searchable"
        :id="name"
        v-model="searchInput"
        type="search"
        :name="name"
        :placeholder="placeholder"
        :class="['w-full sm:text-sm shadow-sm rounded border border-gray-300', errors.length ? 'border-red-500 text-red-600 focus:ring-red-500 focus:border-red-500 placeholder-red-400' : 'focus:ring-gray-500 focus:border-gray-500 placeholder-gray-400', appearance === 'search' ? 'pr-3 pl-8' : 'pl-3 pr-8']"
        @focus="onFocus"
        @blur="onFocusOut"
        @keyup="keyMonitor"
      >
      <button
        v-else
        :id="name"
        type="button"
        :class="['sm:text-sm shadow-sm rounded border border-gray-300 w-full px-3 py-2 text-left', errors.length ? 'border-red-500 text-red-600 focus:outline-none focus:ring-1 focus:ring-red-500 focus:border-red-500' : 'focus:outline-none focus:ring-1 focus:ring-gray-500 focus:border-gray-500']"
        @focus="onFocus"
        @blur="onFocusOut"
      >
        {{ placeholder ? placeholder : 'Select object' }}
      </button>

      <span v-if="appearance === 'search'" class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 text-gray-400" viewBox="0 0 20 20" fill="currentColor">
          <path fill-rule="evenodd" d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z" clip-rule="evenodd" />
        </svg>
      </span>

      <span v-else class="flex absolute inset-y-0 right-0 items-center pr-2 pointer-events-none">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-4 w-4 text-gray-500"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7" />
        </svg>
      </span>

      <ul
        v-if="showOptions"
        :class="['absolute z-10 mt-1 w-full min-w-full w-full bg-white shadow-lg max-h-72 rounded py-1 text-base ring-1 ring-black ring-opacity-5 overflow-auto focus:outline-none sm:text-sm hide-scrollbar']"
        tabindex="-1"
        role="list"
        aria-labelledby="list-label"
      >
        <!--
          Select option, manage highlight styles based on mouseenter/mouseleave and keyboard navigation.
          Highlighted: "text-white bg-indigo-600", Not Highlighted: "text-gray-900"
        -->
        <li
          v-if="filteredOptions.length < 1"
          class="relative py-2 pr-9 pl-3 text-gray-400 cursor-default select-none"
        >
          No data
        </li>
        <li
          v-for="(option, index) in filteredOptions"
          :id="'listbox-option-' + index"
          :key="index"
          class="relative py-2 pr-3 pl-3 text-gray-800 hover:text-gray-900 hover:bg-gray-50 cursor-default select-none cursor-pointer"
          role="option"
          @mousedown="select(option)"
        >
          <div class="flex items-center space-x-3">
            <div>
              <!-- Label -->
              <span class="block font-normal truncate">
                {{ option.label }}
              </span>

              <!-- Description -->
              <span v-if="option.description" class="text-xs text-gray-400">
                {{ option.description }}
              </span>
            </div>
          </div>
        </li>
      </ul>
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
  </div>
</template>
<script>
import { ref, computed, watch } from '@nuxtjs/composition-api'
export default {
  name: 'InputSelect',
  props: {
    htmlTag: {
      type: String,
      default: 'div'
    },
    searchable: {
      type: Boolean,
      default: false
    },
    options: {
      type: Array,
      default: () => [],
      note: 'Available properties: image, label, description, value'
    },
    value: {
      type: Object,
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
    },
    clearOnSelect: {
      type: Boolean,
      default: false
    },
    appearance: {
      type: String,
      default: 'select'
    }
  },
  emits: [
    'update:modelValue',
    'blur'
  ],
  setup (props, { emit }) {
    const optionsList = ref(props.options ? props.options : [])
    const searchInput = ref('')
    const showOptions = ref(false)
    const selected = ref('')

    const filteredOptions = computed(() => {
      return props.options.filter((option) => {
        if (
          typeof option === 'object' &&
          !Array.isArray(option) &&
          option !== null
        ) {
          let result
          if (searchInput.value !== undefined && option.label.toLowerCase().includes(searchInput.value.toLowerCase())) {
            result = option.label.toLowerCase().includes(searchInput.value.toLowerCase())
          }
          if (searchInput.value !== undefined && option.description && option.description.toLowerCase().includes(searchInput.value.toLowerCase())) {
            result = option.description.toLowerCase().includes(searchInput.value.toLowerCase())
          }
          return result
        } else {
          return option.toLowerCase().includes(searchInput.value.toLowerCase())
        }
      })
    })

    const onFocus = () => {
      showOptions.value = true
      emit('on-focus')
    }

    const onFocusOut = () => {
      showOptions.value = false

      if (!selected.value) {
        selected.value = null
      } else if (
        typeof selected.value === 'object' &&
        !Array.isArray(selected.value)
      ) {
        if (props.clearOnSelect === true) {
          searchInput.value = ''
        } else {
          searchInput.value = selected.value.label
        }
      } else if (props.clearOnSelect === true) {
        searchInput.value = ''
      } else {
        searchInput.value = selected.value
      }
    }

    const select = (value) => {
      selected.value = value
      if (
        typeof selected.value === 'object' &&
        !Array.isArray(selected.value) &&
        selected.value !== null
      ) {
        console.log(value.label)
        searchInput.value = value.label
      } else {
        console.log('false')
        searchInput.value = value
      }
      emit('input', value)
      emit('on-select', value)
      emit('change')
    }

    const keyMonitor = (e) => {
      if (e.key === 'Enter' && filteredOptions.value[0]) { select(filteredOptions.value[0]) }

      if (e.key === 'Backspace' && searchInput.value === '') {
        selected.value = ''
        emit('input', selected.value)
      }
    }

    watch(
      () => props.value,
      (value) => {
        selected.value = value
      }
    )

    return {
      optionsList,
      searchInput,
      showOptions,
      filteredOptions,
      selected,
      onFocus,
      onFocusOut,
      select,
      keyMonitor
    }
  }
}
</script>

<style>
input[type="search"]::-webkit-search-decoration,
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-results-button,
input[type="search"]::-webkit-search-results-decoration {
  -webkit-appearance:none;
}
</style>
