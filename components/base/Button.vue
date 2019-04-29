<template>
  <button
    class="bg-blue hover:bg-blue-dark text-white font-bold py-2 px-4"
    @click="submit()"
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
