<template>
  <div class="compteur">
    <h2>Exo 4 : compteur + computed</h2>
    <section>
      <button @click="decrementer(10)">-</button>
      <p>le nombre : {{ nombre }}</p>
      <button @click="incrementer(44)">+</button>
      <p>{{ bug }}</p>
  </section>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ExoCompteur',
  data() {
    return {
      nombre : 10,
      userName: "",
    };
  },
  computed: {
    //V1
    // bug() {
    //   console.log("fonction blablabla")
    //   return this.userName == "" ? "test" : "test 2"
    // },
    //V2
    bug(){
      console.log("fonction exécutée");
      if (this.userName === "") {
        return "test"
      }
      else {
        return "un autre test"
      }
    }
  },
  methods: {
    incrementer(valeur) {
      this.nombre += valeur
      // this.nombre++; 
    },
    decrementer(valeur) {
      this.nombre -= valeur
      // this.nombre--;
    },
  }
});
</script>

<style scoped lang="css">
.compteur {
  background-color: aquamarine;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
.compteur section {
  display: flex;
  justify-content: center;
  &>*{
    margin: 10px;
  }
}
</style>