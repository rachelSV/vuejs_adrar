<script setup>
import UnAmi from '../components/UnAmi.vue'
import ExoDynamicStyle from '../components/ExoDynamicStyle.vue'
import ExoListVifVfor from '../components/ExoListVifVfor.vue'
import ExoDataBiding from '../components/ExoDataBiding.vue'
import ExoCompteur from '../components/Compteur.vue'
import TaskList from '../components/TaskList.vue'
import FormEvent from '../components/FormEvent.vue'
import VModel from '../components/VModel.vue'
import StyleDynamic from '../components/StyleDynamic.vue'
import JeuCompteur from '../components/JeuCompteur.vue'
</script>

<template>
  <div>
    <h1>Exercices</h1>
    <UnAmi leNom="Michel" lePhone="00.00.00" leMail="michel@michel.com"/>
    <UnAmi leNom="Jean Jacques" lePhone="11.11.11" leMail="JJ@jacquy.com"/>
    <StyleDynamic />
    <JeuCompteur />
    <VModel />
    <FormEvent />
    <TaskList />
    <ExoListVifVfor />
    <ExoDynamicStyle />
    <ExoCompteur />
    <ExoDataBiding />
  </div>
</template>
