<template>
  <TheMenu />
  <main>
    <div class="notices">
      <img src="@/assets/truck.svg" />
      <span class="advice">
        ¡Contrata hoy y obtén <b>los mejores beneficios</b>
      </span>
    </div>
    <TheCarousel />
  </main>
</template>

<script setup lang="ts">
import TheMenu from './components/TheMenu.vue';
import TheCarousel from './components/TheCarousel.vue';

</script>

<style lang="css">
</style>
