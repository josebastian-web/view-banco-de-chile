<template>
  <div class="menu">
    <img class="logo" src="@/assets/logo.svg"/>
    <div class="menu-items">
      <TheButton
        v-for="item in menuItems"
        :key="item.name" :text="item.name"
        :href="item.route"
        btn
        uppercase
        class="items" />
    </div>
    <TheButton class="btn-hire" href="#" :text="textForButton" btn uppercase type="primary"/>
    <div class="menu-mobile">
      <TheButton @click="toggleMenu" href="#" icon="menu.svg" btn/>
    </div>
    <nav v-if="openMenu">
      <ul>
        <li v-for="item in menuItems" :key="item.name">
          <a :href="item.route">{{ item.name }}</a>
        </li>
      </ul>
    </nav>

  </div>
</template>

<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue';
import TheButton from './TheButton.vue';

interface MenuItem {
  name: string;
  route: string;
}

const openMenu = ref<boolean>(false);
const menuItems = ref<MenuItem[]>([
  {
    name: 'Productos y Servicios',
    route: '#'
  },
  {
    name: 'Como Contratar',
    route: '#'
  },
  {
    name: 'Beneficios',
    route: '#'
  },
]);

const toggleMenu = () => {
  openMenu.value = !openMenu.value;
};

const windowWidth = ref(window.innerWidth);

const handleResize = () => {
  windowWidth.value = window.innerWidth;
};

onMounted(() => {
  window.addEventListener('resize', handleResize);
});

onUnmounted(() => {
  window.removeEventListener('resize', handleResize);
});

const textForButton = computed(() => {
  if (windowWidth.value >= 1440) {
    return 'Quiero contratar';
  } else if (windowWidth.value > 768) {
    return 'Contratar';
  } else {
    return 'Contratar';
  }
});

</script>

<style lang="css">
</style>
