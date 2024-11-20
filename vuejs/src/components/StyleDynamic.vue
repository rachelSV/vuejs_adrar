<template>
  <div class="style-dynamic">
    <h2>Exercice 7 : style dynamique</h2>
    <div>
      <h4>Carte 1 avec balise style</h4>
      <p :style="{ backgroundColor: colorCarte1, color: 'white' }" @click="clickCarte1">Card Title</p> <!--J'écris le style en dur direct dans une balise :style / puis j'applique le changement au click-->
    </div>
    <div>
      <h4>Carte 2 avec class</h4>
      <p v-bind:class="{ color:isRed }"
      @click="clickCarte2">Card Title</p> <!--J'applique la class color (assignée à rouge dans le CSS) qui est assignée à isRed (isRed est en true dans les data donc la carte est rouge nativement) / au click, le isRed devient fausse donc la classe s'enlève-->
    </div>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'StyleDynamic',
  
  data() {
    return {
      colorCarte1: "blue", //La carte 1 est nativement bleu
      isRed : true //La carte 2 est nativement rouge
    };
  },
  computed: {
  },
  watch: {
  },
  methods: {
    //V1 Si la couleur actuelle est "blue", elle devient "green" au clique. Sinon (si elle est verte dans l'exemple) elle retourne à "blue".
    clickCarte1(){
      this.colorCarte1 = this.colorCarte1 === "blue" ? "green" : "blue";
    },
    //V2 
    // clickCarte1() {
    //   if (this.colorCarte1 === "blue") {
    //   this.colorCarte1 = "green";
    //   } else {
    //   this.colorCarte1 = "blue";
    //   }
    // },

    // Quand la carte 2 est cliquée, isRed passe à false
    clickCarte2(){
      this.isRed = !this.isRed;
    }
  },
});
</script>

<style scoped lang="css">
.style-dynamic{
  background-color: bisque;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
.color { 
  background-color: red;
}
</style>