<template>
  <div class="ma-4">
    <h2>Notifikasi</h2>
    <v-list>
      <v-list-item style="border:1px solid black" class="my-1" v-for="i in 5" :key="i">
        <v-icon large>mdi-file-document</v-icon>
        <v-list-item-content class="ml-3">
          <v-list-item-title>Jangan lupa isi absen dan laporan !</v-list-item-title>
          <v-list-item-subtitle>04 April 2022</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>

<script>
export default {
  name: 'Notifikasi',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
  },
  data: () => ({
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