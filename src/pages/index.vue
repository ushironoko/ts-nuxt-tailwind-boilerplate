<template>
  <section class="container">
    <div class="card">
      <Button text="modal show" :handle-click="modalShow" :disabled="false" />
      <Button text="dialog show 1" :handle-click="dialogShow1" :disabled="false" />
      <Button text="dialog show 2" :handle-click="dialogShow2" :disabled="false" />
      <Modal :name="modalName" :draggable="true" :text="modalText" />
      <Dialog
        :isShow="isDialogShow1"
        title="こんにちは"
        text="これはダイアログ１です"
        firstButtonTitle="1"
        :firstButtonHandleClick="alert1"
        secondButtonTitle="2"
        :secondButtonHandleClick="alert2"
      />

      <Dialog
        :isShow="isDialogShow2"
        title="こんにちは"
        text="これはダイアログ２です"
        firstButtonTitle="1"
        :firstButtonHandleClick="alert1"
        secondButtonTitle="2"
        :secondButtonHandleClick="alert2"
      />
    </div>
  </section>
</template>

<script lang="ts">
import Vue from 'vue'
import Button from '~/components/base/BaseButton.vue'
import Modal from '~/components/base/BaseModal.vue'
import Dialog from '~/components/base/BaseDialog.vue'

export default Vue.extend({
  components: {
    Button,
    Modal,
    Dialog
  },
  data() {
    return {
      modalName: 'sampleModal',
      modalText: 'こんにちは',
      isDialogShow1: false,
      isDialogShow2: false
    }
  },
  methods: {
    modalShow() {
      this.$modal.show(this.modalName)
    },
    alert1() {
      alert('ダイアログのボタン１')
    },
    alert2() {
      alert('ダイアログのボタン２')
    },
    dialogShow1() {
      this.isDialogShow1 = !this.isDialogShow1
    },
    dialogShow2() {
      this.isDialogShow2 = !this.isDialogShow2
    }
  }
})
</script>

<style>
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}

.card {
  @apply max-w-sm rounded overflow-hidden shadow-lg;
}
</style>
