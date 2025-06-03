<template>
  <div class="carousel">
    <div class="carousel-body">
      <div class="cover-image">
        <div class="base-img"></div>
      </div>
      <div class="content-carousel">
        <span class="content-text">
          Hazte cliente empresa del Banco de Chile y <b>obtén tu producto a costo $0*</b>
        </span>
        <div class="buttons">
          <TheButton href="#" text="Quiero contratar" btn uppercase type="primary" size="large"/>
          <TheButton href="#" text="Nuestras tarifas" btn outlined uppercase size="large"/>
        </div>
        <div class="actions">
          <TheButton href="#" icon="arrow-back.svg" btn outlined borderless type="secondary" size="large"/>
          <TheButton href="#" icon="arrow-foward.svg" btn outlined borderless type="secondary" size="large"/>
          <TheButton href="#" icon="pause.svg" btn outlined borderless size="large"/>
        </div>
      </div>
    </div>
    <div class="actions-mobile">
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
