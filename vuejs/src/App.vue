<script setup>
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
import TaskList from './components/TaskList.vue'
import ExoDataBiding from './components/ExoDataBiding.vue'
import ExoCompteur from './components/Compteur.vue'
import FormEvent from './components/FormEvent.vue'
import { RouterView } from 'vue-router'
</script>

<template>
  <NavBar />
  <FormEvent />
  <ExoCompteur />
  <ExoDataBiding />
  <TaskList />
  <RouterView />
  <Footer />
  
</template>

<style scoped></style>
