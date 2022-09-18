<template>
  <div class="ma-4">
    <center><h2>Data Diri</h2></center>
    <h4>Nama Lengkap</h4>
    <v-text-field solo></v-text-field>
    <h4>Jenis Kelamin</h4>
    <v-text-field solo></v-text-field>
    <h4>Tanggal Lahir</h4>
    <v-text-field solo></v-text-field>
    <h4>NIK</h4>
    <v-text-field solo></v-text-field>
    <h4>Agama</h4>
    <v-text-field solo></v-text-field>
    <h4>Program Studi</h4>
    <v-text-field solo></v-text-field>
    <h4>Sekolah / Universitas</h4>
    <v-text-field solo></v-text-field>
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
  name: 'DataDiri',
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