<script setup>
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
import TaskList from './components/TaskList.vue'
import { RouterView } from 'vue-router'
</script>

<template>
  <NavBar />
  <TaskList />
  <RouterView />
  <Footer />
  
</template>

<style scoped></style>
