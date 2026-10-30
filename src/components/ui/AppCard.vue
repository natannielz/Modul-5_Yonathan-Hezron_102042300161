<template>
  <div class="app-card"><slot /></div>
</template>

<style scoped>
.app-card {
  background: white;
  border: 1px solid var(--border-color);
  border-radius: var(--space-4);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.03);
}
</style>
