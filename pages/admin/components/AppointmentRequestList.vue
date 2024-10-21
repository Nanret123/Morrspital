<template>
  <div class="h-full">
    <div class=" flex-1 h-full bg-white shadow-lg rounded-lg p-4">
      <div class="flex justify-between py-2" v-for="(item, index) in items" :key="index.id">
        <div class="flex mr-10">
          <img :src="item.image" alt="picture" class="rounded-full h-[50px] w-[50px] object-cover" />
          <div class="ml-2.5">
            <h3>{{ item.name }}</h3>
            <span>{{ item.age }} {{ item.gender }} {{ item.dateTime }}</span>
          </div>
        </div>
        <!-- Button with dynamic background based on status -->
      <div
        :class="[
          'p-1 flex justify-center items-center rounded h-[42px] w-[99px]',
          getStatusClass(item.status)
        ]"
      >
        <button class="w-full h-full">{{ item.status }}</button>
      </div>

      </div>
    </div>
    <div></div>
  </div>
</template>

<script setup>
const items = [
  { id: 1, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male', status: 'confirmed' },
  { id: 2, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male', status: 'rejected' },
  { id: 3, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male', status: 'confirmed' },
  { id: 4, name: 'Victor Mike', age: 34, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male', status: 'confirmed' }
]

// Function to return a class based on status
const getStatusClass = (status) => {
  switch (status) {
    case 'confirmed':
      return 'bg-green-500';
    case 'rejected':
      return 'bg-red-500';
    case 'pending':
      return 'bg-yellow-500';
    default:
      return 'bg-gray-500';
  }
}
</script>