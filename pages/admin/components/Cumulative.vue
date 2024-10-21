<script setup>
// Accept the items array as a prop
defineProps({
  items: {
    type: Array,
    required: true
  },
  button: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="bg-white ">
    <div class="flex justify-between pb-5">
      <div>
        <span class="pb-2.5 block text-2xl font-semibold">Welcome, Mr Victor</span>
        <span>have a lovely day at work</span>
      </div>
      <div>
        <button class=" text-white p-3 rounded-md w-[150px]" style="background-color: #5D5FEF">{{ button }}</button>
      </div>
    </div>
    <div class="flex flex-wrap gap-5">
      <div v-for="(item, index) in items" :key="index.id">
        <div class="w-[240px] px-5 py-4 rounded-md flex justify-start items-center text-white" :style="{backgroundColor: item.color}">
          <div class="flex justify-center items-center bg-violet-500 rounded-full w-[50px] h-[50px] text-center">
            <Icon name="bx:bxs-group"  class="text-2xl" style="color: black;"  />
          </div>
          <div class="ml-2">
            <h3 class="text-2xl font-semibold">{{ item.number }}</h3>
            <span class="text-nowrap"> {{ item.text }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>