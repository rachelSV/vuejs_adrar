<template>
  <div class="taskList">
    <h1>Exercice 1 - créer une liste de tâches</h1>
    <h2>TaskList (VUE)</h2>
    <p>Ajouter des Task</p>
    <input placeholder="Rajouter la Task" v-model="valeurInput">
    <button @click="addTask()">Ajouter</button>
    <h4>Ma Liste :</h4>
    <ul>
      <li v-for="task in tasks" :key="task">
        {{ task }}
      </li>
    </ul>

    <!-- Exercice 2 afficher différentes variables -->
     <div>
      <h2>Exercice 2 - Différentes variables :</h2>
      <p>Chaine de caractère : {{ stringExemple }}</p>
      <p>Nombre : {{ numberExemple }}</p>
      <p>Tableau : {{ arrayExemple }}</p>
      <p>Objet : {{ objectExemple }}</p>
      <p>Fonction : {{ exercice2(objectExemple) }}</p>
     </div>

     <!-- Exercice 3 nombre aléatoire -->
     <h3>Message : {{ randomNumber() }}</h3>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'TaskList',
  data() {
    return {
      valeurInput: "",
      tasks: [ ],
      // Variables différents types
      stringExemple : "Exemple chaine de caractère",
      numberExemple: 1000,
      arrayExemple: ["bla", "blabla", "blablabl"],
      objectExemple: {
        name: "Michel",
        age: 100
      },

    };
  },
  methods: {
    addTask() {
      this.tasks.push(this.valeurInput)
    },
    // Fonction exercice 2 variables différents types
    exercice2(person) {
      return `Bonjour, ${person.name}`;
    },
    // V1 nombre aléatoire
    randomNumber() {
      return Math.random() > 0.5 ? "Message 1" : "Message 2"
    }
    // V2 nombre aléatoire
    // randomNumber(){
    //  const number = Math.random();
    //  if (number > 0.5) {
    //    return "Message 1 avec IF";
    //  } else {
    //    return "Message 2 avec IF";
    //  }
    // }
  },
});
</script>


<style scoped lang="css">
.taskList {
  background-color: aquamarine;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
.taskList button {
  background-color: blue;
}
</style>