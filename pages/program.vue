<template>
  <div>
    <app-bar />
    <div>Program</div>
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
  }),
  methods: {
  },
  created(){
    // this.getUser()
  },
}
</script>
