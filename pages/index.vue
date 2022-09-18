<template>
  <div>
    <app-bar />
    <v-img style="width:100vw;height:90vh" src="/Asabri.jpg">
    <div class="white--text" style="margin-left:20%;margin-top:6%">
      <h1>
        ASABRI Internship <br> Program
      </h1>
      <div class="mt-6">
        Program magang yang dilaksanakan secara berkala di <br>
        lingkungan PT ASABRI (Persero) untuk memberikan <br>
        pengalaman bekerja kepada generasi penerus mulai dari <br>
        siswa/i SMA se-derajat hingga Mahasiswa S1. 
      </div>
    </div>
    </v-img>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  name: 'IndexPage',
  components: {
    AppBar: () =>
      import(/* webpackChunkName: "app-bar" */ '@/components/AppBar.vue'),
  },
  data: () => ({
    listUser:[],
    email:'',
    password:'',
    value:true,
  }),
  methods: {
    ...mapActions({
      setAlert: 'alert/set',
      setAuth: 'auth/set',
    }),
    async login(){
      const data = JSON.stringify({
        email:this.email,
        password:this.password
      })
      await this.$axios
        .post('/login', data,{
          headers: { 'content-type': 'application/json' },
        })
        .then((res) => {
          let user = {
            email:this.email,
            token:res.data.token
          }
          this.$cookies.set('user', JSON.stringify(user))
          this.setAlert({
            status: true,
            color: 'success',
            text: 'Berhasil Login',
          })
          this.$router.push('/users')
        })
        .catch((error) => {
          let responses = error.response.data
          this.setAlert({
            status: true,
            color: 'error',
            text: responses.error,
          })
        })
    }
    // async getUser(){
    //   var params = new URLSearchParams();
    //   var request = {
    //       params: params
    //   };
    //   await this.$axios
    //       .get('/users',request)
    //       .then((response) => {
    //         this.listUser = response.data.data
    //         console.log('list user', this.listUser)
    //       })
    //       .catch((error) => {
    //           let responses = error.response.data
    //           console.log(responses.api_message)
    //       })
    // }
  },
  created(){
    // this.getUser()
  },
}
</script>
