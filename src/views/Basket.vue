<template>
  <div>
    <h2>In my basket :</h2>
    <table >
      <tr><td>Name</td><td>Code</td><td>% Mortality</td></tr>
      <tr v-for="(v,index) in $store.state.basket" :key="index">
        <td>{{v.name}}</td><td>{{v.code}}</td><td>{{v.mortalite}}</td>
      </tr>
    </table>
    <button @click="$store.commit('move_basket_to_lab')">Send to the lab</button>
  </div>
</template>

<script>

  import {Virus} from "../model";
  import {mapMutations} from "vuex";

  export default {
    name: 'Basket',
    props: ['operation','name','code'],
    computed: {
      ...mapMutations(["move_basket_to_lab"])
    }
  }
</script>

<style scoped>
</style>
