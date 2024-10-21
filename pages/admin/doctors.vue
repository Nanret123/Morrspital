<script setup>
const items = [
  { id: 1, name: 'Victor Mike', profession: 'Cardiologist', image: '/images/spongebob.png' },
  { id: 2, name: 'Stephen Balogun', profession: 'Dentist', image: '/images/spongebob.png' },
  { id: 3, name: 'Scarlet Witch', profession: 'Ophthalmologist', image: '/images/spongebob.png' },
  { id: 3, name: 'Scarlet Witch', profession: 'Ophthalmologist', image: '/images/spongebob.png' },
  { id: 3, name: 'Scarlet Witch', profession: 'Ophthalmologist', image: '/images/spongebob.png' },

]

import SideMenu from './components/SideMenu.vue';
import SearchBar from './components/SearchBar.vue';
</script>



<template>
  <div class="flex">
    <SideMenu />
    <div class="flex flex-col flex-1 w-full h-full">
      <SearchBar />
      <div class="h-full">
        <div class="flex justify-between items-center my-4 px-[30px] py-3">
          <div>
            <span class="text-2xl font-bold mb-6">Doctors</span>
          </div>
          <button type="submit"
            class="h-10 w-32 text-sm font-medium text-white bg-blue-500 rounded-lg hover:bg-blue-600 focus:outline-none focus:shadow-outline">
            Add Doctor
          </button>
        </div>
        <div class="px-[30px] py-3 flex flex-wrap gap-5">
          <div class="" v-for="(item, index) in items" :key="item.id">
            <div class="w-[155px] h-42 p-2 bg-white border border-gray-200 rounded-lg shadow">
              <div class="flex flex-col items-center">
                <img :src="item.image" alt="Profile Picture" class="w-20 h-20 mb-3 rounded-full shadow-lg" />
                <h5 class="mb-1 font-medium text-gray-900">{{ item.name }}</h5>
                <span class="text-sm text-gray-500 dark:text-gray-400">{{ item.profession }}</span>
              </div>
            </div>
       </div>
        </div>
      </div>
    </div>
  </div>
</template>