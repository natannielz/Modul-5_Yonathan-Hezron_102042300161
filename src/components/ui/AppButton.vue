<script setup>
defineProps({
  variant: { type: String, default: 'primary' }, // 'primary' | 'secondary'
  type: { type: String, default: 'button' }
})
</script>

<template>
  <button :type="type" :class="['app-btn', `app-btn-${variant}`]">
    <slot />
  </button>
</template>

<style scoped>
.app-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 12px 24px;
  border-radius: 12px;
  font-weight: 600;
  font-size: 0.95rem;
  cursor: pointer;
  border: 1px solid transparent;
  transition: background 0.2s, transform 0.1s;
}
.app-btn-primary { background: var(--primary); color: white; }
.app-btn-primary:hover:not(:disabled) { background: var(--primary-hover); }
.app-btn-secondary { background: var(--bg-gray); color: var(--text-main); border-color: var(--border-color); }
.app-btn:disabled { cursor: not-allowed; opacity: 0.65; }
</style>
