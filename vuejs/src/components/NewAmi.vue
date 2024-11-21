<template>
  <div class="new-ami">
    <h3>Exercice NewAmi emit</h3>
    <form v-on:submit.prevent="submitData">
      <input v-model="enteredName" type="text" placeholder="nom"><br>
      <input v-model="enteredPhone" type="text" placeholder="téléphone"><br>
      <input v-model="enteredMail" type="text" placeholder="email"><br>
      <button type="sumbit">Envoyer</button>
    </form>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'NewAmi',
  components: {
  },
  props: {
  },
  emits: [
    "add-ami"
  ],
    // v-model event with validation
    // 'update:modelValue': (value) => value !== null,
  data() {
    return {
      enteredName : "",
      enteredPhone : "",
      enteredMail : "",
    };
  },

  methods: {
    submitData(){
      console.log("envoie submit");
      this.$emit("add-ami", this.enteredName, this.enteredPhone, this.enteredMail)
    }
  },
});
</script>

<style scoped lang="css">
.new-ami {
  background-color: bisque;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
</style>