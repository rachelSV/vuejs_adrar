<template>
  <div class="form">
    <h2>{{ name }}</h2>
    <p>{{ age }} ans</p>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'TPactiveUser',

  components: {
  },

  props: {
    name : {
      type: String,
      required: true,
    },
    age : {
      type : Number,
      required: true,
    } 
  },

  emits: {
  },

  data() {
    return {
    };
  },

  methods: {
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