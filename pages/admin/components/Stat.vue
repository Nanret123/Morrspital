<template>
  <div class=" w-[350px] flex flex-col flex-1">
    <div class="flex justify-between mb-2">
      <span>{{ title }}</span>
      <span>{{ month }}</span>
    </div>
    <div class="bg-white h-full shadow-lg rounded-lg p-4">
      <div class="flex justify-between gap-2">
        <div class="flex items-center justify-center w-[40px] h-[40px] rounded-full bg-violet-700 text-center ">
          <Icon name="bx:bxs-group" style="color: black;" class="text-lg" />
        </div>
        <div class="flex flex-col">
          <span class="font-medium text-nowrap">{{ name1 }}</span>
          <span class="font-semibold">{{ name1Number }}</span>
        </div>
        <div>
          <div>
            <Icon name="bx:line-chart" style="color: green;" />
          </div>
          <span class="text-emerald-400">{{ name1Growth }}%</span>
        </div>
      </div>
      <div class="flex justify-between gap-2 mt-7">
        <div class="flex items-center justify-center w-[40px] h-[40px] rounded-full bg-violet-700 text-center ">
          <Icon name="bx:bxs-group" style="color: black;" class="text-lg" />
        </div>
        <div class="flex flex-col">
          <span class="font-medium text-nowrap">{{ name2 }}</span>
          <span class="font-semibold">{{ name2Number }}</span>
        </div>
        <div>
          <div>
            <Icon name="bx:line-chart" style="color: green;" />
          </div>
          <span class="text-emerald-400">{{ name2Growth }}%</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Define props for dynamic data
defineProps({
  title: {
    type: String,
    required: true
  },
  month: {
    type: String,
    required: true
  },
  name1: {
    type: String,
    required: true
  },
  name1Number: {
    type: Number,
    required: true
  },
  name1Growth: {
    type: Number,
    required: true
  },
  name2: {
    type: String,
    required: true
  },
  name2Number: {
    type: Number,
    required: true
  },
  name2Growth: {
    type: Number,
    required: true
  }
})
</script>
