<template>
  <component :is="htmlTag">
    <label
      v-if="label"
      :for="name"
      class="block mb-1 text-sm"
    >
      {{ label }} <span v-if="required" class="text-red-600">*</span>
    </label>
    <input
      type="text"
      :id="name"
      :placeholder="placeholder"
      @input="$emit('input', $event.target.value)"
      @blur="$emit('blur')"
      :class="['sm:text-sm shadow-sm rounded border border-gray-300', errors.length ? 'border-red-500 text-red-600 focus:ring-red-500 focus:border-red-500 placeholder-red-400' : 'focus:ring-gray-500 focus:border-gray-500 placeholder-gray-400']"
    >

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
export default {
  name: 'InputText',
  props: {
    htmlTag: {
      type: String,
      default: 'div'
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
    }
  }
}
</script>
