<script setup lang="ts">
defineProps<{
  date: string
  position: string
  company: string
}>()
</script>

<template>
  <div class="timeline-item">
    <div class="date">{{ date }}</div>
    <div class="description">
      <h3>{{ position }}</h3>
      <div class="company">{{ company }}</div>
      <div class="details">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<style scoped>
.timeline-item {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: flex-start;

  &:not(:last-child) {
    margin-bottom: var(--grid-gap-2);
  }
}
.date {
  font-weight: bold;
  margin-right: var(--grid-gap-2);
}

.description {
  flex-grow: 1;
}

.company {
  font-style: italic;
}
</style>
