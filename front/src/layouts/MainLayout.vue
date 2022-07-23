<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="toolbar">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title class="header-title">
          Artemis Academy
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Artemis Academy
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-footer elevated class="toolbar-footer">
      <q-toolbar class="footer">
        <div class="text-footer">
          Desenvolvido por <a href="https://github.com/lopessx"> @lopessx </a> e <a href="https://github.com/Porfirio-Prodigy"> @Porfirio-Prodigy</a>
        </div>
      </q-toolbar>
    </q-footer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Matérias',
    caption: 'Voltado para o meio Acadêmico.',
    icon: 'school',
    link: '/materias'
  },
  {
    title: 'Complementar',
    caption: 'Conhecimentos altamente demandados.',
    icon: 'auto_stories',
    link: '/complementar'
  },
  {
    title: 'Desenvolvimento',
    caption: 'Voltado para o desenvolvimento pessoal e profissional',
    icon: 'psychology',
    link: '/desenvolvimento'
  },
  {
    title: 'Github',
    caption: 'Artemis Github',
    icon: 'code',
    link: 'https://github.com/lopessx/artemis-quasar'
  }

]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
