<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="app">
    <nav class="flex space-x-10 px-4 py-4  bg-pink-100">
      <router-link to="/todos">Pendentes</router-link>
      <router-link to="/completed">Concluídas</router-link>
    </nav>    
    <router-view />
  </div>
</template>
