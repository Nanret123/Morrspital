<script setup>
import SideMenu from '@/pages/admin/components/SideMenu.vue'
import SearchBar from './components/SearchBar.vue';
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

const menuItems = [
  { id: 1, title: 'Doctors', icon: 'bi:person-fill', link: '/admin/doctors' },
  { id: 2, title: 'Patients', icon: 'bi:person-fill', link: '/admin/patients' },
  { id: 3, title: 'Appointments', icon: 'bi:person-fill', link: '/admin/appointments' },
  { id: 4, title: 'Schedule Timings', icon: 'bi:person-fill', link: '/admin/schedule-timings' },
  { id: 5, title: 'Departments', icon: 'bi:person-fill', link: '/admin/departments' },
  { id: 6, title: 'Employees', icon: 'bi:person-fill', link: '/admin/employees' },
  { id: 7, title: 'Accounts', icon: 'bi:person-fill', link: '/admin/accounts' },
  { id: 8, title: 'Payroll', icon: 'bi:person-fill', link: '/admin/payroll' },
  { id: 9, title: 'Chats', icon: 'bi:person-fill', link: '/admin/chats' },
  { id: 10, title: 'Calls', icon: 'bi:person-fill', link: '/admin/calls' },
  { id: 11, title: 'Email', icon: 'bi:person-fill', link: '/admin/emails' },
  { id: 12, title: 'Blog', icon: 'bi:person-fill', link: '/admin/blog' },
  { id: 13, title: 'Assets', icon: 'bi:person-fill', link: '/admin/assets' },
  { id: 14, title: 'Logout', icon: 'bi:person-fill', link: '/admin/logout' },

]
</script>

<template>
  <div class="flex">
    <SideMenu :menuItems="menuItems" />
    <div class="flex flex-col flex-1 w-full h-full">
      <SearchBar />
      <div class="bg-background h-full p-[30px]">
        <Cumulative :items="items" button="Add Patient" />
        <div class="flex my-5 gap-4 flex-wrap">
          <SalesChart class="flex-1 w-[250px]" />
          <Stat class="flex-1 w-full" :title="'Patients'" :month="'August'" :name1="'New Patients'" :name1Number="40300"
            :name1Growth="8.5" :name2="'Old Patients'" :name2Number="40300" :name2Growth="8.5" />
          <GenderChart class="flex-1 w-[250px] h-[350px]" />
        </div>
        <Request />
      </div>
    </div>
  </div>
</template>