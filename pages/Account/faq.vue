<template>
  <div class="ma-4">
    <h2>Apa yang ingin kamu ketahui ?</h2>
    <v-expansion-panels class="mt-3" multiple>
      <v-expansion-panel v-for="(item,index) in faq" :key="index">
        <v-expansion-panel-header><h3>{{ item.nama }}</h3></v-expansion-panel-header>
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
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </div>
</template>

<script>
export default {
  name: 'Faq',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
  },
  data: () => ({
    faq:[
      {nama:'Bagaimana jika saya lupa password ?'},
      {nama:'Setiap berapa kali pengecekan laporan harian ?'},
      {nama:'Berapa uang saku yang didapatkan ?'},
      {nama:'Bagaimana jika saya lupa password ?'},
      {nama:'Bagaimana jika saya lupa password ?'},
    ],
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