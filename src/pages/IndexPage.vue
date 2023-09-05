<template>
  <q-page padding>
    <input v-model="message" @keyup="handleKeyup" />
    <button @click="clearMessage">Clear</button>
    <h5>{{ message }}</h5>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      message: 'I love Vue.js!'
    }

  },
  methods: {
    clearMessage() {
      this.message = ''
    },
    handleKeyup(e) {
      if (e.keyCode == 27) {
        this.clearMessage()
      }
      else if (e.keyCode == 13) {
        this.alertMessage()
      }
    },
    alertMessage() {
      alert(this.message)
    }
  }
})
</script>
