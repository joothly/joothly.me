<script setup lang="ts">
defineProps<{
  heading?: string
  justifyContent?: boolean
}>()
</script>

<template>
  <div class="info-box" :class="{ 'justify-content': justifyContent }">
    <h2 class="heading" v-if="heading">{{ heading }}</h2>
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.info-box {
  position: relative;
  padding: var(--grid-gap);
  background: var(--color-background);
  border: var(--border-width) var(--border-style) var(--color-border);
  border-radius: var(--border-radius);
  box-shadow: var(--shadow);

  &.justify-content>.content {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  &.header-box>.content {
    display: flex;
    flex-direction: column;

    @media (min-width: 1024px) {
      flex-direction: row;
    }
  }
}

.heading {
  margin-top: 0;
  margin-bottom: var(--heading-space);
  font-size: var(--heading-size);
  font-weight: var(--heading-weight);
  text-transform: var(--heading-transform);
}
</style>
