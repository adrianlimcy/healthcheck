<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Health Check App
        </q-toolbar-title>

        <div>Ricoh SG App V1.0</div>
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
          Essential Links
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Health Check',
    caption: 'How healthy is your company?',
    icon: 'health_and_safety',
    link: '/'
  },
  // {
  //   title: 'Facebook',
  //   caption: 'Ricoh Facebook Page',
  //   icon: 'public',
  //   link: 'https://www.facebook.com/RicohSG'
  // },
  {
    title: 'Benchmark',
    caption: 'How you fare against market',
    icon: 'equalizer',
    link: '/benchmark'
  },
  {
    title: 'About Health Check',
    caption: 'Community Ricoh project',
    icon: 'favorite',
    link: '/about'
  }
];

import { defineComponent, ref } from 'vue'

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
