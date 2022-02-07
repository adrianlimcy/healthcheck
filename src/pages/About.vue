<template>
  <q-page class="q-pa-md">
    <div class="q-pa-md">
      <div class="q-gutter-y-md">
        <q-card class="my-card">
            <div class="q-gutter-y-md flex flex-center">
                <img src="~/assets/ricoh-logo.svg">
            </div>

            <q-card-section>
                <div class="text-h6">Our Future Workplace</div>
                <div class="text-subtitle2">by Ricoh</div>
            </q-card-section>

            <q-card-section class="q-pt-none">
                This is a Ricoh Singapore prototype app
            </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PageIndex',
  setup () {
  },

})
</script>
<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 250px
</style>