<script setup>
import SideMenu from '@/pages/admin/components/SideMenu.vue'
import SearchBar from './components/SearchBar.vue';
import Cumulative from './components/Cumulative.vue';;
import Request from './components/Request.vue';
import SalesChart from './components/SalesChart.vue';
import GenderChart from './components/GenderChart.vue';
import Stat from './components/Stat.vue';
import AppointmentRequestList from './components/AppointmentRequestList.vue';

const items = [
  { id: 1, number: '8, 234', text: 'Appointments' },
  { id: 2, number: '8, 234', text: 'Total Patients' },
  { id: 3, number: '8, 234', text: 'Clinic consulting' },
  { id: 4, number: '8, 234', text: 'Total Users' },
]

const doctors = [
  { id: 1, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male' },
  { id: 2, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male' },
  { id: 3, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male' },
  { id: 4, name: 'Victor Mike', age: 34, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male' }
]


</script>
<template>
  <div class="flex">
    <SideMenu />
    <div class="flex flex-col flex-1 w-full h-full">
      <SearchBar />
      <div class="bg-slate-400 h-full p-[30px]">
        <Cumulative :items="items" button="Add Patient" />
        <div class="flex my-5 gap-4 flex-wrap">
          <div class="flex-1">
            <div class="flex justify-between">
              <span>Appointment Request</span>
              <button class="flex items-center text-cyan-300 p-2 rounded-md">
                View All
                <Icon name="ant-design:right-outlined" />
              </button>
            </div>
            <AppointmentRequestList />
          </div>

          <div class="flex-1 flex flex-col gap-5">
            <div>
              <Stat class="flex-1 w-full" :title="'Patients'" :month="'August'" :name1="'New Patients'"
                :name1Number="40300" :name1Growth="8.5" :name2="'Old Patients'" :name2Number="40300"
                :name2Growth="8.5" />
            </div>
            <GenderChart class="flex-1 w-[250px] h-[350px]" />
          </div>
          <div class="flex-1 flex flex-col">
            <span class="mb-2">Todays Appointments</span>
            <div class=" bg-white shadow-lg rounded-lg p-4">
              <div class="flex justify-between py-2" v-for="(item, index) in doctors" :key="index.id">
              <div class="flex mr-10">
                <img :src="item.image" alt="picture" class="rounded-full h-[50px] w-[50px] object-cover" />
                <div class="ml-2.5">
                  <h3>{{ item.name }}</h3>
                  <span>{{ item.age }} {{ item.gender }}</span>
                </div>
              </div>
              <div class="text-green-500">  {{ item.dateTime }}</div>
          </div>
            </div>
          <div>calender</div>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>