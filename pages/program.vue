<template>
  <div>
    <app-bar />
    <br>
    <v-container>
      <div>
        <h2>Program Internship</h2>
        <br>
        <div style="width:80%;margin:0 auto" class="d-flex justify-space-between">
          <v-card width="30%" v-for="(item,index) in program" :key="index">
            <div class="ma-3">
              <div style="height:40px">
                <h3>{{item.nama}}</h3>
              </div>
              <br>
              <div style="color:#FFCD38">
                Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
              </div>
            </div>
          </v-card>
        </div>
      </div>
    </v-container>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  name: 'Program',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
  },
  data: () => ({
    program:[
      {nama:'Praktik Kerja Lapangan'},
      {nama:'Gerakan Nasional Indonesia Kompeten'},
      {nama:'Program Magang Mahasiswa Bersertifikat'},
    ]
  }),
  methods: {
  },
  created(){
    // this.getUser()
  },
}
</script>
