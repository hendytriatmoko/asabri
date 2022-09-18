<template>
  <div>
    <v-row>
        <v-col cols="12" sm="3" style="min-height:100vh">
            <v-list style="background:none;position:fixed;width:20%">
                <v-list-item-group>
                    <v-list-item v-for="item in listProfil" :to="item.route" :key="item.route">
                        <v-icon class="mr-1" color="#0A2A62">{{ item.icon }}</v-icon>
                        <v-list-item-title>{{item.text}}</v-list-item-title>
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
export default {
  name: 'Profil',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
  },
  data: () => ({
    listProfil:[
        { text: 'Data diri', icon:'mdi-account-outline', route: '/account/profil/data-diri' },
        { text: 'Kontak', icon:'mdi-account-outline', route: '/account/profil/kontak' },
        { text: 'Dokumen', icon:'mdi-account-outline', route: '/account/profil/dokumen' },
        { text: 'Rekening Pribadi', icon:'mdi-account-outline', route: '/account/profil/rekening-pribadi' },
        { text: 'Media Sosial', icon:'mdi-account-outline', route: '/account/profil/media-sosial' },
        { text: 'Ganti Password', icon:'mdi-account-outline', route: '/account/profil/ganti-password' },
    ]
  }),
  methods: {
  },
  created(){
    // this.getUser()
  },
}
</script>

<style>

</style>