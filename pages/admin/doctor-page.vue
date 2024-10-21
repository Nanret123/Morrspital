<script setup>
import SideMenu from '@/pages/admin/components/SideMenu.vue'
import SearchBar from './components/SearchBar.vue';
import Cumulative from './components/Cumulative.vue';;
import Request from './components/Request.vue';
import SalesChart from './components/SalesChart.vue';
import GenderChart from './components/GenderChart.vue';
import Stat from './components/Stat.vue';
import AppointmentRequestList from './components/AppointmentRequestList.vue';
import TodayAppointment from './components/Today-Appointment.vue';
import DatePicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css';
import { ref } from 'vue';

definePageMeta({
  layout: 'default',
})

const selectedDate = ref < Date | null > (null);

const items = [
  { id: 1, number: '8,234', text: 'Appointments', color: '#5D5FEF' },  // Blue
  { id: 2, number: '8,234', text: 'Total Patients', color: '#FFA901' },   // Green
  { id: 3, number: '8,234', text: 'Clinic Consulting', color: '#FF5363' }, // Yellow
  { id: 4, number: '8,234', text: 'Total Users', color: '#24A8FA' },   // Red
];

const menuItems = [
  { id: 1, title: 'Appointments  ', icon: 'bi:person-fill', link: '/doctor/appointments' },
  { id: 2, title: 'My Patients', icon: 'bi:person-fill', link: '/doctor/my-patients' },
  { id: 3, title: 'Payments', icon: 'bi:person-fill', link: '/doctor/payments' },
  { id: 4, title: 'Messages', icon: 'bi:person-fill', link: '/doctor/messages' },
  { id: 5, title: 'Calls', icon: 'bi:person-fill', link: '/doctor/calls' },
  { id: 6, title: 'Settings', icon: 'bi:person-fill', link: '/doctor/settings' },
  { id: 7, title: 'Sign Out', icon: 'bi:person-fill', link: '/doctor/sign-out' },

]
</script>

<template>
  <div class="flex">
    <SideMenu :menuItems="menuItems" />
    <div class="flex flex-col flex-1 w-full h-full">
      <SearchBar />
      <div class="bg-background h-full p-[30px]">
        <Cumulative :items="items" button="Add Patient" />
        <div class="flex my-5 gap-4 flex-wrap h-[300px]">
          <div class="flex flex-col flex-1">
            <div class="flex justify-between p-2">
              <span>Appointment Request</span>
              <span>View All
                <Icon name="bx:bxs-chevron-right" style="color: black;" />
              </span>
            </div>
            <AppointmentRequestList />
          </div>
          <div class="pt-2 flex flex-col gap-3">
            <Stat class="flex-1 w-full" :title="'Patients'" :month="'August'" :name1="'New Patients'"
              :name1Number="40300" :name1Growth="8.5" :name2="'Old Patients'" :name2Number="40300" :name2Growth="8.5" />
            <GenderChart class="flex-1 w-[240px] h-[350px]" />
          </div>
          <div class="flex flex-col gap-3">
            <TodayAppointment />
            <DatePicker v-model="selectedDate" :inline="true" :is-required="true" placeholder="Select a date" />

          </div>
        </div>
      </div>
    </div>
  </div>
</template>