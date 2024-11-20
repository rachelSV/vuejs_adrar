<template>
  <div class="v-model">
    <h2>Exercice 5 : v-model mardi 19</h2>
    <p>v-on + v-bind</p>
    <input v-on:keyup="afficherUserName" v-bind:value="nameUser" type="text">
    <p>{{ nameUser }}</p>
    <p>v-model</p>
    <input v-model="userName" type="text">
    <p>{{ userName }}</p>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'VModel',
  data() {
    return {
      nameUser : "",
      userName : "",
    };
  },
  methods: {
    afficherUserName(e) {
      this.nameUser = e.target.value
    }
  },
});
</script>

<style scoped lang="css">
.v-model {
  background-color: aquamarine;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
</style>