<script setup>
import Navbar from '@/components/app/Navbar.vue'
</script>

<template>
  <Navbar />
  <main class="dashboard-container">
    <nav class="dash-nav">
      <router-link to="/dashboard">Overview</router-link>
      <router-link to="/dashboard/events">Event Management</router-link>
    </nav>
    <router-view />
  </main>
</template>

<style scoped>
.dashboard-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: var(--space-8) var(--space-6);
}
.dash-nav {
  display: flex;
  gap: var(--space-6);
  margin-bottom: var(--space-6);
}
.dash-nav a {
  color: var(--text-muted);
  font-weight: 600;
  text-decoration: none;
}
.dash-nav a.router-link-exact-active {
  color: var(--primary);
}
</style>
