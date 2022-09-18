<template>
  <div>
    <h2>Laporan Sharing Knowledge</h2>
    <div>
      <div>
        Silahkan upload laporan bulanan kamu di sini. <br>
        Ketentuan laporan bulanan dapat kamu dapatkan di sini. <br><br>

        Ketentuan laporan: <br>
        Format pdf <br>
        File maksimal berukuran 10MB
      </div>
      <v-card elevation="0" rounded="lg" style="height:200px;border:1px dashed #0A2A62" class="d-flex align-center justify-center mt-3">
        <center>
        <v-icon x-large>mdi-file-document</v-icon>
        </center>
      </v-card>
      <v-card-actions>
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
    bulanDipilih:'',
  }),
  methods: {
    async getTanggal(){
        console.log('tgl', this.picker)
        this.bulanDipilih = this.picker
    }
  },
  created(){
    // this.getUser()
  },
}
</script>

<style>

</style>