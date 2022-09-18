<template>
  <div>
    <div class="pa-4" v-if="pilihKegiatan == ''">
      <h2>Kegiatanku</h2>
      <v-expansion-panels multiple class="mt-3">
        <v-expansion-panel v-for="(item,index) in kegiatanku" :key="index">
          <v-expansion-panel-header style="color:#FFCD38">{{ item.nama }}</v-expansion-panel-header>
          <v-expansion-panel-content>
            <div>
              Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
              Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown 
              printer took a galley of type and scrambled it to make a type specimen book. It has survived 
              not only five centuries, but also the leap into electronic typesetting, remaining essentially 
              unchanged. It was popularised in the 1960s with the release of Letraset sheets containing 
              Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker 
              including versions of Lorem Ipsum.
            </div>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="#0A2A62" class="white--text" @click="pilihKegiatan = item.nama">submit</v-btn>
            </v-card-actions>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </div>
    <div class="ma-4" v-else>
      <v-btn elevation="0" @click="pilihKegiatan = ''">
        <v-icon>mdi-chevron-left</v-icon>
        Sebelumnya
      </v-btn>
      <div>
        <laporan-harian v-if="pilihKegiatan == 'LAPORAN HARIAN'" />
        <laporan-bulanan v-if="pilihKegiatan == 'LAPORAN BULANAN'" />
        <belajar-mandiri v-if="pilihKegiatan == 'LAPORAN BELAJAR MANDIRI'" />
        <sharing-knowledge v-if="pilihKegiatan == 'LAPORAN SHARING KNOWLEDGE'" />
        <laporan-akhir v-if="pilihKegiatan == 'LAPORAN AKHIR'" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Kegiatan',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
    LaporanBulanan: () =>
      import(/* webpackChunkName: "laporan-bulanan" */ '@/components/LaporanBulanan.vue'),
    LaporanHarian: () =>
      import(/* webpackChunkName: "laporan-harian" */ '@/components/LaporanHarian.vue'),
    BelajarMandiri: () =>
      import(/* webpackChunkName: "belajar-mandiri" */ '@/components/BelajarMandiri.vue'),
    SharingKnowledge: () =>
      import(/* webpackChunkName: "sharing-knowledge" */ '@/components/SharingKnowledge.vue'),
    LaporanAkhir: () =>
      import(/* webpackChunkName: "laporan-akhir" */ '@/components/LaporanAkhir.vue'),
  },
  data: () => ({
    kegiatanku:[
      {nama:'LAPORAN HARIAN'},
      {nama:'LAPORAN BULANAN'},
      {nama:'LAPORAN BELAJAR MANDIRI'},
      {nama:'LAPORAN SHARING KNOWLEDGE'},
      {nama:'LAPORAN AKHIR'},
    ],
    
    pilihKegiatan:'',
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