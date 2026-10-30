<script setup>
import Navbar from '@/components/app/Navbar.vue'
</script>

<template>
  <Navbar />
  <main class="page-container">
    <router-view />
  </main>
</template>

<style scoped>
.page-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: var(--space-8) var(--space-6);
}
</style>
