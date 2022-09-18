<template>
  <div class="ma-4">
    <h2>Absen</h2>
    <div v-if="tglDipilih == ''">
        <v-date-picker width="100%" v-model="picker"></v-date-picker>
        <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn @click="getTanggal()">Pilih</v-btn>
        </v-card-actions>
    </div>
    <div v-else class="mt-3">
      <center>
        <v-btn @click="tglDipilih=''" color="#0A2A62" class="white--text">
            {{ tglDipilih }}
        </v-btn>
      </center>
      <h4>Nama</h4>
      <v-text-field outlined dense></v-text-field>
      <h4>Unit Kerja</h4>
      <v-select label="Pilih unit kerja" v-model="unitKerja" solo dense :items="listUnitKerja"></v-select>
      <h4>Keterangan</h4>
      <v-select label="Pilih Keterangan" v-model="keterangan" solo dense :items="listKeterangan"></v-select>
      <h4>Absensi</h4>
      <v-select label="pilih jenis absen" v-model="absen" solo dense :items="listAbsen"></v-select>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn rounded="xl" color="#FFCD38">Submit</v-btn>
      </v-card-actions>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Absen',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
  },
  data: () => ({
    picker:(new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
    tglDipilih:'',
    listUnitKerja:['SEKPER','DIVISI BANGBIS','DIVISI LAYANAN','DIVISI UMUM','DIVISI YANSUM'],
    listAbsen:['ABSEN MASUK','ABSEN PULANG'],
    listKeterangan:['WORK FROM OFFICE(WFO)','WORK FROM HOME(WFH)','TIDAK KERJA KARENA IZIN','TIDAK KERJA KARENA SAKIT'],
    unitKerja:'',
    absen:'',
    keterangan:'',

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