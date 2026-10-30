<script setup>
defineProps({ modelValue: { type: String, default: '' } })
defineEmits(['update:modelValue'])
</script>

<template>
  <input
    class="search-bar"
    type="search"
    placeholder="Search events by title or location..."
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>

<style scoped>
.search-bar {
  width: 100%;
  padding: 12px 16px;
  margin-bottom: var(--space-4);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  font-size: 1rem;
  outline: none;
}
.search-bar:focus {
  border-color: var(--primary);
  box-shadow: 0 0 0 3px rgba(102, 68, 255, 0.15);
}
</style>
