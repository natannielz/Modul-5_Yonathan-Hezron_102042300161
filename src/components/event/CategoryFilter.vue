<script setup>
defineProps({
  categories: { type: Array, required: true },
  modelValue: { type: String, default: 'All' }
})
defineEmits(['update:modelValue'])
</script>

<template>
  <div class="category-filter">
    <button
      v-for="cat in categories"
      :key="cat"
      :class="['chip', { active: modelValue === cat }]"
      @click="$emit('update:modelValue', cat)"
    >
      {{ cat }}
    </button>
  </div>
</template>

<style scoped>
.category-filter { display: flex; gap: var(--space-2); flex-wrap: wrap; }
.chip {
  padding: 6px 16px;
  border-radius: 50px;
  border: 1px solid var(--border-color);
  background: white;
  color: var(--text-muted);
  font-weight: 600;
  cursor: pointer;
}
.chip.active { background: var(--primary); border-color: var(--primary); color: white; }
</style>
