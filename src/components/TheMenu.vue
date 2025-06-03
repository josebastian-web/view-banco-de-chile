<template>
  <div class="flex flex-row justify-around items-center md:justify-between xl:justify-between menu">
    <img class="logo" src="@/assets/logo.svg"/>
    <div class="hidden md:flex md:flex-row xl:flex xl:flex-row menu-items">
      <TheButton
        v-for="item in menuItems"
        :key="item.name" :text="item.name"
        :href="item.route"
        uppercase
        class="items"
      />
    </div>
    <TheButton class="btn-hire" href="#" :text="textForButton" uppercase type="primary" />
    <div class="flex md:hidden xl:hidden menu-mobile">
      <TheButton @click="toggleMenu" href="#" icon="menu.svg" btn />
    </div>
    <Transition name="fade-height" mode="out-in">
      <nav v-if="openMenu">
        <ul>
          <li v-for="item in menuItems" :key="item.name">
            <TheButton :href="item.route" :text="item.name" uppercase />
          </li>
        </ul>
      </nav>
    </Transition>
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
.fade-height-enter-active,
.fade-height-leave-active {
  transition: all 0.2s;
  max-height: 230px;
}
.fade-height-enter,
.fade-height-leave-to
{
  opacity: 0;
  max-height: 0px;
}
</style>
