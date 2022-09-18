<template>
  <div class="ma-4">
    <center><h2>Kontak</h2></center>
    <h4>Email</h4>
    <v-text-field solo></v-text-field>
    <h4>No. Telpon</h4>
    <v-text-field solo></v-text-field>
    <h4>No. Telpon Orang Tua</h4>
    <v-text-field solo></v-text-field>
    <h4>Alamat</h4>
    <v-textarea solo></v-textarea>
    <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn rounded="xl" color="#FFCD38">Simpan</v-btn>
      </v-card-actions>
  </div>
</template>

<script>
export default {
  name: 'Kontak',
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