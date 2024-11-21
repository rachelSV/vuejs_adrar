<template>
  <div class="form">
    <p>Formulaire d'édition</p>
    <input v-model="name" type="text" placeholder="nom" /> <br>
    <input v-model="age" type="number" placeholder="age" /> <br>
    <button @click="majUser">MAJ des données</button>
  </div>
</template>



<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'TPuserData',

  components: {
  },

  props: {
  },

  emits: [
    "maj-user"
  ],

  data() {
    return {
      name: "",
      age: "",
    };
  },

  methods: {
    majUser() {
        this.$emit("maj-user", this.name, this.age );
      }
  },
});
</script>


<style scoped lang="css">
.form {
  background-color: aquamarine;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
</style>