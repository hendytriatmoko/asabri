<template>
  <div class="ma-4">
    <center><h2>Media Sosial</h2></center>
    <h4>LinkedIn</h4>
    <v-text-field solo></v-text-field>
    <h4>Instagram</h4>
    <v-text-field solo></v-text-field>
    <h4>Twitter</h4>
    <v-text-field solo></v-text-field>
    <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn rounded="xl" color="#FFCD38">Simpan</v-btn>
      </v-card-actions>
  </div>
</template>

<script>
export default {
  name: 'MediaSosial',
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