<template>
  <div class="flex flex-col items-center justify-start carousel">
    <div class="flex flex-col xl:flex-row-reverse md:flex-row-reverse carousel-body">
      <div class="cover-image">
        <div class="base-img"></div>
      </div>
      <div class="flex flex-col items-center justify-center content-carousel">
        <span class="content-text">
          Hazte cliente empresa del Banco de Chile y <b>obtén tu producto a costo $0*</b>
        </span>
        <div class="flex flex-col items-center xl:flex-row buttons">
          <TheButton href="#" text="Quiero contratar" btn uppercase type="primary" size="large"/>
          <TheButton href="#" text="Nuestras tarifas" btn outlined uppercase size="large"/>
        </div>
        <div class="hidden xl:flex items-center actions">
          <TheButton href="#" icon="arrow-back.svg" btn outlined borderless type="secondary" size="large"/>
          <TheButton href="#" icon="arrow-foward.svg" btn outlined borderless type="secondary" size="large"/>
          <TheButton href="#" icon="pause.svg" btn outlined borderless size="large"/>
        </div>
      </div>
    </div>
    <div class="flex flex-row items-center justify-center xl:hidden actions-mobile">
      <TheButton href="#" icon="arrow-back.svg" btn outlined borderless type="secondary" size="large"/>
      <TheButton href="#" icon="arrow-foward.svg" btn outlined borderless type="secondary" size="large"/>
      <TheButton href="#" icon="pause.svg" btn outlined borderless size="large"/>
    </div>
  </div>
</template>

<script setup lang="ts">
import TheButton from './TheButton.vue';

</script>

<style lang="css">
</style>
