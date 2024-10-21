<script setup>
const items = [
  { id: 1, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male' },
  { id: 2, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male' },
  { id: 3, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male' },
  { id: 4, name: 'Victor Mike', age: 34, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male' }
]

import Stat from './Stat.vue';
</script>


<template>
  <div class="flex flex-wrap justify-between gap-5">
    <div class="flex-1 bg-white shadow-lg rounded-lg p-4">
      <div class="flex justify-between items-center">
        <h3>Appointment Request</h3>
        <button class="flex items-center text-cyan-300 p-2 rounded-md">
          View All
          <Icon name="ant-design:right-outlined" />
        </button>
      </div>
      <div class="flex justify-between py-2" v-for="(item, index) in items" :key="index.id">
        <div class="flex mr-10">
          <img :src="item.image" alt="picture" class="rounded-full h-[50px] w-[50px] object-cover" />
          <div class="ml-2.5">
            <h3>{{ item.name }}</h3>
            <span>{{ item.age }} {{ item.gender }} {{ item.dateTime }}</span>
          </div>
        </div>
        <div>
          <button class="mr-2">
            <Icon name="ant-design:edit-outlined" class="text-lg" />
          </button>
          <button>
            <Icon name="bx:trash" style="color:red" class="text-lg" />
          </button>
        </div>
      </div>
    </div>
    <div class=" flex-1 bg-white shadow-lg rounded-lg p-4">
      <div class="flex justify-between items-center">
        <h3>Doctors</h3>
        <button class="flex items-center text-cyan-300 p-2 rounded-md">
          View All
          <Icon name="ant-design:right-outlined" />
        </button>
      </div>
      <div class="flex justify-between py-2" v-for="(item, index) in items" :key="index.id">
        <div class="flex mr-10">
          <img :src="item.image" alt="picture" class="rounded-full h-[50px] w-[50px] object-cover" />
          <div class="ml-2.5">
            <h3>{{ item.name }}</h3>
            <span>{{ item.age }} {{ item.gender }} {{ item.dateTime }}</span>
          </div>
        </div>
      </div>
    </div>
    <div class="flex-1">
      <Stat class="w-full h-full" 
      :title="'Finances'" 
      :month="'August'" 
      :name1="'Total Income'" 
      :name1Number="40300"
      :name1Growth="8.5" 
      :name2="'Total Expenses'" 
      :name2Number="40300" 
      :name2Growth="8.5" />
    </div>
  </div>
</template>