<template>
  <a :href="href" :class="buttonClasses">
    <img v-if="icon" class="icon" :src="getIconPath(icon)" alt="icon" />
    <span v-if="text">{{ text }}</span>
  </a>
</template>

<script setup lang="ts">
import { computed } from 'vue';

interface Props {
  href: string;
  uppercase?: boolean;
  outlined?: boolean;
  icon?: string;
  text?: string;
  size?: 'large' | 'small';
  type?: 'primary' | 'secondary';
  borderless?: boolean;
}

const props = defineProps<Props>();

const buttonClasses = computed(() => ({
  'flex': true,
  'items-center': true,
  'justify-center': true,
  'btn': true,
  'uppercase': props.uppercase,
  'btn-outlined': props.outlined,
  'btn-primary': props.type === 'primary',
  'btn-secondary': props.type === 'secondary',
  'borderless': props.borderless,
  'btn-large': props.size === 'large'
}));

const getIconPath = (iconName: string) => {
  return new URL(`/src/assets/${iconName}`, import.meta.url).href;
};

</script>

<style lang="css">

</style>
