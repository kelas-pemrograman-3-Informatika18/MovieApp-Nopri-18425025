<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white text-indigo-10">
      <q-toolbar>
        <q-btn dense flat round @click="leftDrawerOpen = !leftDrawerOpen" icon="menu"/>
        <q-space></q-space>
        <q-btn flat round>
          <q-avatar>
          <q-img src="~assets/ddplk9t-1b198c3d-d63d-4125-aa12-0c1e5aff9870.png"/>
          </q-avatar>
          <q-menu>
          <q-list style="min-width: 100px">
            <q-item clickable v-close-popup :to="{ name: 'profiles' }">
              <q-item-section>Profile</q-item-section>
            </q-item>
            <q-item clickable v-close-popup @click="logout()">
              <q-item-section>Logout</q-item-section>
            </q-item>
          </q-list>
          </q-menu>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      content-class="text-white bg-primary"
    >
      <q-scroll>
        <q-scroll-area class="fit">
          <q-list>
            <q-item class="justify-center text-center q-mt-md q-mb-md">
              <div>
                <q-avatar size="120px">
                  <q-img src="~assets/ddplk9t-1b198c3d-d63d-4125-aa12-0c1e5aff9870.png"/>
                </q-avatar>
                <div class="text-weight-bold q-mt-md">{{ $q.localStorage.getItem('datauser').namaLengkap }}</div>
                <div>Aplikasi Penjualan Film</div>
              </div>
            </q-item>

            <q-item clickable active-class="active" v-ripple exact :to="{ name: 'dashboardAdmin' }">
              <q-item-section avatar>
                <q-icon name="dashboard"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Dashboard</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable active-class="active" v-ripple exact :to="{ name: 'dataDVD' }">
              <q-item-section avatar>
                <q-icon name="play_circle_filled"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Data DVD</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable active-class="active" v-ripple exact :to="{ name: 'inputBarang' }">
              <q-item-section avatar>
                <q-icon name="input"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Input DVD</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable active-class="active" v-ripple exact :to="{ name: 'dataUser'}">
              <q-item-section avatar>
                <q-icon name="supervisor_account"/>
              </q-item-section>
              <q-item-section>
                <q-item-label>Data User</q-item-label>
              </q-item-section>
            </q-item>

          </q-list>
        </q-scroll-area>
      </q-scroll>
    </q-drawer>

    <q-page-container class="bg-grey-1">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',

  components: {
  },

  data () {
    return {
      leftDrawerOpen: false
    }
  },
  methods: {
    logout () {
      this.$q.localStorage.remove()
      this.$router.push({ name: 'loginpage' })
    }
  }
}
</script>
<style scoped>
.active{
  color: #000;
  background: #fafafa;
  padding-right: 10px;
}
</style>
