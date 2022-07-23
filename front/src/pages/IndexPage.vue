<template>
  <q-page class="flex flex-center">
    <h6>Welcome To Artemis</h6>
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
