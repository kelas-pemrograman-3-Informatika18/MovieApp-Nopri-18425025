<template>
<div class="fixed-center">
  <q-card class="my-card" bordered>
      <q-item>
        <q-item-section avatar>
          <q-avatar>
            <img src="https://cdn.quasar.dev/img/boy-avatar.png">
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label>Profil Anda</q-item-label>
        </q-item-section>
      </q-item>

      <q-separator />

      <q-card-section horizontal>
        <q-card-section>
          Nama Lengkap
        </q-card-section>

        <q-separator vertical />

        <q-card-section class="text-center">
         {{ $q.localStorage.getItem('datauser').namaLengkap }}
        </q-card-section>
      </q-card-section>
            <q-separator horizontal />

      <q-card-section horizontal >
        <q-card-section style="width: 126px">
          Username
        </q-card-section>

        <q-separator vertical />

        <q-card-section>
         {{ $q.localStorage.getItem('datauser').username }}
        </q-card-section>
      </q-card-section>

      <q-separator horizontal />

      <q-card-section horizontal >
        <q-card-section style="width: 126px">
          E-Mail
        </q-card-section>

        <q-separator vertical />

        <q-card-section>
         {{ $q.localStorage.getItem('datauser').email }}
        </q-card-section>
      </q-card-section>

      <q-separator horizontal />
    </q-card>

</div>
  </template>
<script>
export default {
  data () {
    return {
      lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
    }
  }
}
</script>
<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 500px
</style>
