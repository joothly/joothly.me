<script setup lang="ts">
import IconWizard from '../components/icons/IconWizard.vue';
import CoinFlip from './CoinFlip.vue';
import InfoBox from './InfoBox.vue';

defineProps<{
  title: string
  subtitle: string
  avatarUrl: string
}>()
</script>

<template>
  <InfoBox class="header-box">
    <div class="text">
      <InfoBox class="title">
        <h1>{{ title }}</h1>
        <p class="subtitle">{{ subtitle }}</p>
        <IconWizard class="icon" />
      </InfoBox>
      <slot></slot>
    </div>
    <CoinFlip :imgSrc="avatarUrl" :imgAlt="title" class="avatar" />
  </InfoBox>
</template>

<style scoped>
.header-box {
  background-color: var(--color-background-hard);
}

.avatar {
  flex-shrink: 0;
  width: 100%;
  max-width: 256px;
  margin-top: var(--grid-gap);

  @media (min-width: 1024px) {
    flex-shrink: 1;
    width: 40%;
    max-width: 300px;
    margin-top: calc(-1 * var(--grid-gap-4) - var(--border-width));
    margin-left: var(--grid-gap);
  }
}

.text {
  width: 100%;
  flex-shrink: 0;

  @media (min-width: 1024px) {
    flex-grow: 1;
    width: auto;
    max-width: calc(100% - 300px);
  }
}

.title {
  width: calc(100% + var(--grid-gap) + var(--border-width) + var(--border-width));
  margin-top: calc(-1 * var(--grid-gap-4) - var(--border-width));
  margin-left: calc(-1 * var(--grid-gap) - var(--border-width));
  margin-bottom: var(--grid-gap);
  padding-top: var(--grid-gap-1);
  padding-bottom: var(--grid-gap-2);

  @media (min-width: 675px) {
    width: 100%;
    max-width: 495px;
  }

  @media (min-width: 1024px) {
    max-width: none;
  }
}

.icon {
  display: none;

  @media (min-width: 1100px) {
    display: block;
  }
}
</style>
