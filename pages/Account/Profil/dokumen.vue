<template>
  <div class="ma-4">
    <center><h2>Dokumen</h2></center>
    <h4>Upload CV</h4>
    <v-card elevation="0" rounded="lg" style="height:100px;border:1px dashed #0A2A62" class="d-flex align-center justify-center mt-3">
      <center>
        <v-icon x-large>mdi-file-document</v-icon>
      </center>
    </v-card>
    <h4 class="mt-6">Upload KHS</h4>
    <v-card elevation="0" rounded="lg" style="height:100px;border:1px dashed #0A2A62" class="d-flex align-center justify-center mt-3">
      <center>
        <v-icon x-large>mdi-file-document</v-icon>
      </center>
    </v-card>
    <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn rounded="xl" color="#FFCD38">Simpan</v-btn>
      </v-card-actions>
  </div>
</template>

<script>
export default {
  name: 'Dokumen',
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