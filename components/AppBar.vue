<template>
  <v-app-bar
      color="#0A2A62"
      fixed
      app
    >
      <v-img style="cursor:pointer" max-width="180px" @click="to('/')" src="/asabri_white.png" alt=""></v-img>
      <v-spacer />
      <v-item-title style="cursor:pointer" class="white--text" @click="to('/')">Beranda</v-item-title>
      <v-item-title style="cursor:pointer" class="ml-3 white--text" @click="to('/program')">Program</v-item-title>
      <v-item-title style="cursor:pointer" class="ml-3 white--text" @click="to('/account/profil')">Hilda Harisa</v-item-title>
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-icon
          v-bind="attrs"
          v-on="on" class="ml-3" color="white" large>mdi-account-circle</v-icon>
        </template>
        <v-list>
          <v-list-item
            v-for="(item, index) in items"
            :key="index"
            :to="item.route"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
</template>

<script>
export default {
  data: () => ({
    dataUser:[],
    items: [
        { title: 'Akunku',route:'/account/profil' },
        { title: 'Notifikasi',route:'/account/notifikasi' },
        { title: 'Keluar' },
      ],
  }),
  methods: {
    to(data){
      this.$router.push(data)
    }
  },
  created(){
    this.dataUser = this.$cookies.get('user')
    console.log('user bar', this.dataUser)
  }
}
</script>

<style>

</style>