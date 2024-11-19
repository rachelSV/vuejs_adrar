<template>
  <div class="card_profil">
    <h2>Exercice 3 DATABiding - Profile User</h2>
    <section>
      <img v-bind:src="source_img" alt="image_profil">
      <p>{{ name }}</p>
      <input type="text" v-bind:value="name">
      <p>{{ age }}</p>
      <p>NB fétiche : {{ randomNumber() }}</p>
      <p>Age + 10 : {{ ageAddition() }}</p>
    </section>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ExoDataBiding',
  data() {
    return {
      source_img: "https://picsum.photos/300/400",
      name : "Michel",
      age : 20,
    };
  },
  methods: {
    randomNumber() {
      return Math.random()
    },
    ageAddition(){
      return this.age + 10
    },  
  },
});
</script>

<style scoped lang="css">
.card_profil {
  background-color: bisque;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
</style>