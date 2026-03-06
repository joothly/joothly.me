<script setup lang="ts">
import { ref } from 'vue';

defineProps<{
  imgSrc: string
  imgAlt: string
}>()

const spinning = ref(false)

function spin() {
  if (spinning.value) return
  spinning.value = true
}
</script>

<template>
  <div class="coin" :class="{ spinning }" @click="spin" @animationend="spinning = false">
    <img :src="imgSrc" :alt="imgAlt" class="coin-front" />
    <div class="coin-back"></div>
  </div>
</template>

<style scoped>
.coin {
  position: relative;
  aspect-ratio: 1;
  cursor: pointer;
  perspective: 300px;
  transform-style: preserve-3d;
  transform-origin: center center;

  &.spinning {
    animation: coin-spin 1.8s ease-out;
  }
}

.coin-front,
.coin-back {
  position: absolute;
  inset: 0;
  border-radius: 50%;
  border: var(--border-width) var(--border-style) var(--color-border);
  backface-visibility: hidden;
}

.coin-front {
  object-fit: cover;
  width: 100%;
  height: auto;
}

.coin-back {
  background-color: var(--c-lilac-light);
  transform: rotateY(180deg);

  @media (min-width: 1024px) {
    height: calc(100% - var(--grid-gap));
  }
}

@keyframes coin-spin {
  0% {
    transform: rotateY(0deg);
  }

  100% {
    transform: rotateY(1080deg);
  }
}
</style>
