<script setup lang="ts">
import { ref } from 'vue'
import InfoBox from './InfoBox.vue'

const showImprint = ref(false)
</script>

<template>
  <InfoBox justifyContent>
    <slot></slot>
    <a href="#" @click.prevent="showImprint = !showImprint">
      <slot name="imprintTrigger"></slot>
    </a>
    <Transition name="imprint">
      <div v-if="showImprint" class="imprint">
        <slot name="imprint"></slot>
      </div>
    </Transition>
  </InfoBox>
</template>

<style scoped>
.imprint {
  width: 100%;
  margin-top: var(--grid-gap);
}

.imprint-enter-active,
.imprint-leave-active {
  transition:
    opacity var(--animation-duration) var(--animation-function),
    max-height var(--animation-duration) var(--animation-function);
  max-height: 200px;
}

.imprint-enter-from,
.imprint-leave-to {
  opacity: 0;
  max-height: 0;
}
</style>
