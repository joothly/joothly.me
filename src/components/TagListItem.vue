<script setup lang="ts">
defineProps<{
  heading: string
  tags: string[]
}>()
</script>

<template>
  <div class="tag-list-item">
    <h3>{{ heading }}</h3>
    <ul class="tags">
      <li v-for="tag in tags" :key="tag" class="tag">{{ tag }}</li>
    </ul>
  </div>
</template>

<style scoped>
.tag-list-item {
  &:not(:last-child) {
    margin-bottom: var(--grid-gap-2);
  }
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: var(--grid-gap-1);
  list-style: none;
  padding: 0;
}

.tag {
  font-size: 0.875rem;
  padding: 0.1rem 0.5rem;
  background-color: color-mix(in srgb, var(--color-border) 20%, transparent);
}
</style>
