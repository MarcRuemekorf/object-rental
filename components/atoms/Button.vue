<template>
  <button type="button" :class="['inline-flex items-center justify-center rounded', buttonVariant, buttonSize]" @click="$emit('click')">
    <slot />
  </button>
</template>
<script>
import { computed } from '@nuxtjs/composition-api';
export default {
  name: 'Button',
  props: {
    variant: {
      type: String,
      default: 'primary'
    },
    size: {
      type: String,
      default: 'sm'
    }
  },

  setup(props) {
    const buttonVariant = computed(() => {
      switch (props.variant) {
        case 'primary' :
          return 'border border-transparent text-white bg-gray-600 hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-gray-500'
        default :
          return 'border border-gray-300 shadow-sm text-gray-700 bg-white hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-gray-500'
      }
    })

    const buttonSize = computed(() => {
      switch (props.size) {
        case 'sm' :
          return 'px-2.5 py-1.5'
        case 'md' :
          return 'px-4 py-2'
        case 'lg' :
          return 'px-6 py-3'
      }
    })

    return {
      buttonVariant,
      buttonSize
    }
  }
}
</script>
