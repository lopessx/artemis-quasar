<template>
  <q-page class="flex flex-center">
    <img
      alt="Quasar logo"
      src="~assets/quasar-logo-vertical.svg"
      style="width: 200px; height: 200px"
    >
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'
import { api } from 'boot/axios.js'

export default defineComponent({
  name: 'IndexPage',

  setup () {
    return {
      first: ref('')
    }
  },

  created () {
    api.get('/')
      .then((response) => {
        console.log(JSON.stringify(response.data))
      })
  }
})
</script>
