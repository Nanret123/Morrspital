<template>
  <div :class="['flex flex-col relative', sideBarClass]">
    <div class="flex my-5 justify-evenly items-center">
      <img src="/images/logo.png" />
      <span :class="['origin-left', hideText]">Morrspital</span>
      <Icon name="gravity-ui:bars" style="color: black" class="w-7 h-7 cursor-pointer" @click="toggleSidebar" />
    </div>

    <ul v-for="(item, index) in menuItems" :key="item.id" class="mb-2 pt-2">
      <NuxtLink :to="item.link"  class="text-grey-300 text-sm flex items-center gap-x-4 cursor-pointer p-2 hover: bg-light-white rounded-md">
        <Icon :name="item.icon" style="color: black" class="text-2xl" />
        <h4 :class="['origin-left', hideText, 'text-sm']">{{ item.title }}</h4>
      </NuxtLink>
    </ul>
  </div>
</template>

<script setup>
import { useState } from '#app';

const isOpen = useState('isOpen', () => true);

const sideBarClass = computed(() => isOpen.value ? 'w-[190px]' : 'w-20');
const hideText = computed(() => isOpen.value ? '' : 'hidden');

const toggleSidebar = () => {
  isOpen.value = !isOpen.value;
}

defineProps({
  menuItems: { type: Array, required: true },
})

</script>