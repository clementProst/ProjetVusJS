<template>
  <div>
    <table>
      <tr><td>Name</td><td>Code</td><td>% Mortality</td></tr>
      <tr v-for="(v,index) in viruses" :key="index"><td>{{v.name}}</td><td>{{v.code}}</td><td>{{v.mortalite}}</td><td> <button @click="$store.commit('clone_to_basket',v)">Clone virus for the lab</button></td></tr>
    </table>
  </div>
</template>

<script>

import {mapMutations, mapState} from "vuex";

  export default {
    name: 'Articles',
    computed: {
      ...mapState(["viruses"]),
      ...mapMutations(["clone_to_basket"])
    }
  }
</script>

<style scoped>
</style>
