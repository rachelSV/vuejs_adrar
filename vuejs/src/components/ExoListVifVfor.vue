<template>
  <div class="taskList">
    <h1>Exercice 9 - liste de courses</h1>
    <p>List de courses</p>
    <input placeholder="Ajouter un truc" v-model="valeurInput">
    <button @click="addTask()">Ajouter</button>
    <h4>Ma Liste :</h4>
    <ul v-if="afficherList">
      <li v-for="(task, index) in tasks" :key="task" @click="suppLigne(index)">
        {{ index }} - {{ task }}
      </li>
    </ul>
    <button @click="masquerList">{{ afficherList ? 'Masquer Liste' : 'Afficher Liste' }}></button>
  </div>
</template> 

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ExoListVifVfor',
  data() {
    return {
      valeurInput: "",
      tasks: [ ],
      afficherList: true, // Par défaut, la liste est affichée
    };
  },
  methods: {
    addTask() {
      this.tasks.push(this.valeurInput)
    },
    suppLigne(index) {
      this.tasks.splice(index, 1);
    },
    masquerList() {
    this.afficherList = !this.afficherList; // Alterne l'état d'affichage de la liste
    },
  },
});
</script>


<style scoped lang="css">
.taskList {
  background-color: bisque;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
.taskList button {
  background-color: rgb(0, 225, 255);
}
</style>