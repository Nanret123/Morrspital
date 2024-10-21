<script setup>

import Cumulative from './components/Cumulative.vue';;
import Request from './components/Request.vue';
import SalesChart from './components/SalesChart.vue';
import GenderChart from './components/GenderChart.vue';
import Stat from './components/Stat.vue';

const items = [
  { id: 1, number: '8,234', text: 'Total Employees', color: '#5D5FEF' },  // Blue
  { id: 2, number: '8,234', text: 'Total Patients', color: '#FFA901' },   // Green
  { id: 3, number: '8,234', text: 'Current Admissions', color: '#FF5363' }, // Yellow
  { id: 4, number: '8,234', text: 'Total Doctors', color: '#24A8FA' },   // Red
];

definePageMeta({
	layout: 'default'
});


</script>

<template>
    <div class="bg-background h-full p-[30px]">
        <Cumulative :items="items" button="Add Admin" />
          <div class="flex my-5 gap-4 flex-wrap">
            <SalesChart class="flex-1 w-[250px]" />
            <Stat class="flex-1 w-full" 
            :title="'Patients'"
            :month="'August'"
            :name1="'New Patients'"
            :name1Number="40300"
            :name1Growth="8.5"
            :name2="'Old Patients'"
            :name2Number="40300"
            :name2Growth="8.5" />
            <GenderChart class="flex-1 w-[250px] h-[350px]" />
          </div>
        <Request />
    </div>
</template>