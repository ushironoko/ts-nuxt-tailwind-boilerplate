<template>
  <v-dialog />
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    isShow: {
      type: Boolean,
      default: false,
      required: true
    },
    title: {
      type: String,
      default: ''
    },
    text: {
      type: String,
      default: ''
    },
    firstButtonTitle: {
      type: String,
      default: ''
    },
    firstButtonHandleClick: {
      type: Function,
      default: () => {}
    },
    secondButtonTitle: {
      type: String,
      default: ''
    },
    secondButtonHandleClick: {
      type: Function,
      default: () => {}
    }
  },
  watch: {
    isShow() {
      this.dialogShow()
    }
  },
  methods: {
    dialogShow() {
      this.$modal.show('dialog', {
        title: this.title,
        text: this.text,
        buttons: [
          {
            title: this.firstButtonTitle,
            handler: () => {
              this.firstButtonHandleClick()
            }
          },
          {
            title: this.secondButtonTitle,
            handler: () => {
              this.secondButtonHandleClick()
            }
          },
          {
            title: 'Close'
          }
        ]
      })
    }
  }
})
</script>
