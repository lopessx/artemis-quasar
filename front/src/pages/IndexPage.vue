<template>
  <q-page class="flex flex-center">
    <CardMaterias></CardMaterias>
    <h6>Welcome To Artemis</h6>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'
import { api } from 'boot/axios.js'
import CardMaterias from '../components/CardMaterias.vue'

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
  },
  components: { CardMaterias }
})
</script>
