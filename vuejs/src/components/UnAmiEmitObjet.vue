<template>
    <div class="un-ami">
      <h1>Exercice EMIT Objet</h1>
      
      <p>{{ leNom }}</p>
  
        <button @click="masquerDetail">
          {{ voirDetail ? 'Masquer Details' : 'Voir Details' }}
        </button>
        <p v-if="voirDetail">{{ lePhone }}</p>
        <p v-if="voirDetail">{{ leMail }}</p>
        <p v-if="voirDetail">{{ premium }}</p>
        <h2>{{ premium == '1' ? 'Ami Premium' : 'Ami Nul' }}</h2> <!-- Si la props premium est à 1, on affiche le 1er message, sinon le deuxième-->
        <button @click="afficherPremium" class="btn btn-danger mb-1">Afficher premium</button>
    </div>
  </template>
  
  <script lang='js'>
  import { defineComponent } from 'vue'
  
  export default defineComponent({
    name: 'UnAmiEmitObjet',
    components: {
    },
    props: ({
        leId : {
          type : String,
          required : true,
        },
       leNom : {
         type: String,
         required: true, //Impose que dans le parent, "leNom" est obligatoire sinon la console soulève un Warning
       },
       lePhone: {
         type: String,
         required: true,
       },
       leMail : {
         type: String,
         required: true,
       },
       premium : {
         type: Boolean,
         required: false,
         default: false,
        //  validator: function(value){return value==='1' || value==='0'} //Permets de faire des conditions et de les faire respecter (là, premium doit être à 0 ou 1 obligatoirement, sinon console affiche Warning)
       }
    }),
    emits: {
      "mon-event-premium" : function(id) {
        if(id){
          return true
        } else {
          console.warn("erreur")
          return false
        }
      }
    },
    data() {
      return {
        voirDetail: true,
        // premiumData : this.premium
      };
    },
    methods: {
      masquerDetail() {
        this.voirDetail = !this.voirDetail;
      },
      afficherPremium() {
        this.$emit("mon-event-premium")
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