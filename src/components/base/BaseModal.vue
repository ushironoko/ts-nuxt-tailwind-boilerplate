<template>
  <modal :name="name" :draggable="draggable">
    <p>{{ text }}</p>
  </modal>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    name: {
      type: String,
      default: ''
    },
    text: {
      type: String,
      default: ''
    },
    draggable: {
      type: Boolean,
      default: false
    }
  }
})
</script>

<style scoped>
p {
  @apply font-sans flex justify-center leading-normal text-center text-grey-darker text-base;
}
</style>
