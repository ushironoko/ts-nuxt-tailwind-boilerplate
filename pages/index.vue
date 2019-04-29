<template>
  <section class="container">
    <div>
      <Button :text="buttonText" :handle-click="alert" />
    </div>
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
import Button from '~/components/base/Button.vue'

export default Vue.extend({
  components: {
    Button
  },
  data() {
    return {
      buttonText: 'submit',
      alertText: 'Hello TS Nuxt!!'
    }
  },
  methods: {
    alert() {
      alert(this.alertText)
    }
  }
})
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
