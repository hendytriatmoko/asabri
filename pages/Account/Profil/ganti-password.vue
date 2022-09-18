<template>
  <div class="ma-4">
    <center><h2>Ganti Password</h2></center>
    <h4>Password Sekarang</h4>
    <v-text-field solo></v-text-field>
    <h4>Password Baru</h4>
    <v-text-field solo></v-text-field>
    <h4>Ulangi Password Baru</h4>
    <v-text-field solo></v-text-field>
    <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn rounded="xl" color="#FFCD38">Simpan</v-btn>
      </v-card-actions>
  </div>
</template>

<script>
export default {
  name: 'GantiPassword',
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