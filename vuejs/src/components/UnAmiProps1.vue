<template>
  <div class="un-ami">
    <h1>Exercice PROPS Tableau - Un Ami</h1>
    <p>{{ leNom }}</p>

      <button @click="masquerDetail">
        {{ voirDetail ? 'Masquer Details' : 'Voir Details' }}
      </button>
      <p v-if="voirDetail">{{ lePhone }}</p>
      <p v-if="voirDetail">{{ leMail }}</p>
      <h2>{{ premium == 1 ? 'Ami Premium' : 'Ami Nul' }}</h2> <!-- Si la props premium est à 1, on affiche le 1er message, sinon le deuxième-->
  </div>
</template>

<script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'UnAmiProps1',
  components: {
  },
  props: [ 
    "leNom",
    "lePhone",
    "leMail",
    "premium"
  ],

  data() {
    return {
      voirDetail: true
      //Scénario d'erreur : on créé la props ici pour pouvoir la modifier
      // premiumData: this.premium
    };
  },
  methods: {
    masquerDetail() {
      this.voirDetail = !this.voirDetail;
    },
    afficherPremium() {
      //Scénarios d'erreur : on ne modifie pas une props (premium) direct. On stock d'abord dans une data
      // this.premium = 1
      // this.premium = this.premium == 1 ? 0 : 1;
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