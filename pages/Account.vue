<template>
  <div>
    <app-bar />
    <v-row no-gutters>
        <v-col cols="12" sm="3" style="background:#0A2A62;min-height:100vh">
            <v-list style="background:none;position:fixed;width:25%">
                <v-list-item-group>
                    <v-list-item v-for="item in menus" :to="item.route" :key="item.route" class="white--text">
                        <v-icon class="mr-1" color="white">{{ item.icon }}</v-icon>
                        {{ item.text }}
                    </v-list-item>
                </v-list-item-group>
            </v-list>
        </v-col>
        <v-col cols="12" sm="9">
            <NuxtChild />
        </v-col>
    </v-row>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  name: 'Program',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
  },
  data: () => ({
    menus: [
      { text: 'Profil', icon:'mdi-account-outline', route: '/account/profil' },
      { text: 'Kegiatanku', icon:'mdi-clipboard-list-outline', route: '/account/kegiatanku' },
      { text: 'Rencana Kerja', icon:'mdi-clipboard-clock-outline', route: '/account/rencana-kerja' },
      { text: 'Absen', icon:'mdi-file-document-check-outline', route: '/account/absen' },
      { text: 'Notifikasi', icon:'mdi-bell-ring-outline', route: '/account/notifikasi' },
      { text: 'Faq', icon:'mdi-frequently-asked-questions', route: '/account/faq' },
    ],
  }),
  methods: {
    ...mapActions({
      setAlert: 'alert/set',
      setAuth: 'auth/set',
    }),
  },
  created(){
    // this.getUser()
  },
}
</script>
