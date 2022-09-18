<template>
  <div>
    <h2>Laporan Harian</h2>
    <div v-if="tglDipilih == ''">
        <v-date-picker width="100%" v-model="picker"></v-date-picker>
        <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn @click="getTanggal()">Pilih</v-btn>
        </v-card-actions>
    </div>
    <div v-else>
      <center>
        <v-btn @click="tglDipilih=''" color="#0A2A62" class="white--text">
            {{ tglDipilih }}
        </v-btn>
      </center>
      <br>
      <v-text-field
        outlined
        label="Masukkan Keterangan"
      ></v-text-field>
      <v-card rounded="lg" style="height:200px" class="d-flex align-center justify-center">
        <center>
        <v-icon>mdi-file-document</v-icon>
        </center>
      </v-card>
      <v-card-actions>
        <v-btn rounded="xl" color="#FFCD38">Edit</v-btn>
        <v-spacer></v-spacer>
        <v-btn rounded="xl" color="#FFCD38">Submit</v-btn>
      </v-card-actions>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LaporanHarian',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
  },
  data: () => ({
    picker:(new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
    tglDipilih:'',
  }),
  methods: {
    async getTanggal(){
        console.log('tgl', this.picker)
        this.tglDipilih = this.picker
    }
  },
  created(){
    // this.getUser()
  },
}
</script>

<style>

</style>