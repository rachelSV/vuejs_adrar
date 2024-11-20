<template>
  <div class="compteur">
    <h2>Exo 6 : Jeu compteur</h2>
    <section>
      <button @click="incrementer(1)">+1</button>
      <button @click="incrementer(5)">+5</button>
      <p>nombre : {{ nombre }}</p>
      <p>{{ afficherMessage }}</p>
      <p v-show="message">t'es allé trop loin</p> <!-- affiche <p> quand dans le watch le nombre arrive à 30 et message devient true-->
  </section>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'JeuCompteur',
  
  data() {
    return {
      nombre : 0, // le nombre démarre à zéro
      message: false // la variable message est caché grâce au v-show
    };
  },

  computed: { // Si nombre est plus petit OU plus grand que 7
    afficherMessage(){
      if (this.nombre < 7 || this.nombre > 7) {
        return "Essai encore"
      } else {
        return "Bravo"
      }
    }
  },
  
  watch: { //Surveille la variable nombre si elle arrive à 30, reinitialise la valeure à 0 au bout de 3 secondes
    nombre(value){
      console.log("le watcher s'active") // Dans la console pour que je me rende compte de quand le watcher s'active
      if(value == 30){ // Si la variable nombre est à 30
        this.message = true; // La variable message passe en true et s'affiche
        setTimeout(() => {
          this.message = "", // quand le setTimeOut s'active, la variable message se vide
          this.nombre = 0; // quand le setTimeOut s'active, la variable nombre revient à 0
        }, 3000);
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
  },
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