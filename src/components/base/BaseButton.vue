<template>
  <button
    class="base-button"
    :class="{ 'disabled': disabled }"
    @click.stop="!disabled && submit()"
  >
    {{ text }}
  </button>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    text: {
      type: String,
      default: ''
    },
    disabled: {
      type: Boolean,
      default: false
    },
    handleClick: {
      type: Function,
      default: () => {}
    }
  },
  methods: {
    submit() {
      this.handleClick()
    }
  }
})
</script>

<style scoped>
.base-button {
  @apply bg-blue text-white font-bold py-2 px-4 rounded;
}

.base-button:hover {
  @apply bg-blue-dark;
}

.disabled {
  @apply opacity-50 cursor-not-allowed;
}

.disabled:hover {
  @apply bg-blue;
}
</style>
