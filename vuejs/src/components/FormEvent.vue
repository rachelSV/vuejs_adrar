<template>
  <div class="form">
    <h2>Exercice 4 - Formulaire avec évènements</h2>
    <form v-on:submit.prevent>
      <input v-on:keyup="getKey" type="text"><br>
      <p>{{ keyValue }}</p>
      <input v-on:keyup.esc="getKey2" type="text"><br>
      <p>{{ keyValue2 }}</p>
      <button v-on:click="popup()">Envoyer</button>
    </form>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'FormEvent',
  data() {
    return {
      keyValue : "",
      keyValue2 : ""
    };
  },
  methods: {
    getKey(e) {
      this.keyValue = e.target.value
    },
    getKey2(e){
      this.keyValue2 = e.target.value
    },
    popup() {
      alert("Coucou") 
    },
  },
});
</script>

<style scoped lang="css">
.form {
  background-color: bisque;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
</style>