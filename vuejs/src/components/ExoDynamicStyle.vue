<template>
  <div class="exo_dynamic">
    <h2>TP : Dynamic Styling Mode</h2>
    <input v-model="input1" type="text">
    <h4 :style="{ display: isVisible ? 'block' : 'none' }" v-bind:class="input1">Hello World (class dynamique)</h4>
    <!-- v-if="isVisible" -->
    <input v-model="input2" type="text">
    <h4 v-bind:style="{ backgroundColor: input2 }">Hello World (couleur dynamique)</h4>
  
    <button @click="clickBouton">Afficher</button>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ExoDynamicStyle',
  
  data() {
    return {
      input1: "", 
      input2: "",
      isVisible: true
    };
  },
  computed: {
  },
  watch: {
  },
  methods: {
    clickBouton(){
      this.isVisible = !this.isVisible;
    }
  },
});
</script>

<style scoped lang="css">
.exo_dynamic {
  background-color: aquamarine;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
.hello {
  background-color: blue;
}
.world {
  background-color: bisque;
}
</style>