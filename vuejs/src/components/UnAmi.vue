<template>
  <div class="un-ami">
    <h1>Exercice PROPS - Un Ami</h1>
    <p>{{ leNom }}</p>

      <button @click="masquerDetail">
        {{ voirDetail ? 'Masquer Details' : 'Voir Details' }}
      </button>
      <p v-if="voirDetail">{{ lePhone }}</p>
      <p v-if="voirDetail">{{ leMail }}</p>
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'UnAmi',
  components: {
  },
  props: [ 
    "leNom",
    "lePhone",
    "leMail"
  ],

  data() {
    return {
      voirDetail: true
    };
  },
  methods: {
    masquerDetail() {
      this.voirDetail = !this.voirDetail;
    }
  },
});
</script>

<style scoped lang="css">
.un-ami {
  background-color: aquamarine;
  margin: 3% 35% 0% 35%;
  text-align: center;
}
</style>