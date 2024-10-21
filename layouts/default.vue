<template>
  <div class="w-full h-screen flex">
  <div class="w-full h-screen flex">
    <SideMenu :menuItems="menuItems" />
<div class="flex flex-col flex-1 ">
      <SearchBar />
   
    <Cumulative :items="items" button="Add Patient" />
      <div class="bg-green-200 h-auto p-10">
       <slot></slot>
      </div>
       </div>
    </div>

  </div>
</template>

<script setup>
import SideMenu from '@/pages/admin/components/SideMenu.vue'
import SearchBar from '@/pages/admin/components/SearchBar.vue'
import Cumulative from '@/pages/admin/components/Cumulative.vue'


const items = [
  { id: 1, number: '8,234', text: 'Appointments', color: '#5D5FEF' },  // Blue
  { id: 2, number: '8,234', text: 'Total Patients', color: '#FFA901' },   // Green
  { id: 3, number: '8,234', text: 'Clinic Consulting', color: '#FF5363' }, // Yellow
  { id: 4, number: '8,234', text: 'Total Users', color: '#24A8FA' },   // Red
];

const menuItems = [
  { id: 1, title: 'Doctors', icon: 'bi:person-fill', link: '/admin/doctors' },
  { id: 2, title: 'Patients', icon: 'bi:person-fill', link: '/admin/patients' },
  { id: 3, title: 'Appointments', icon: 'bi:person-fill', link: '/admin/appointments' },
  { id: 4, title: 'Schedule Timings', icon: 'bi:person-fill', link: '/admin/schedule-timings' },
  { id: 5, title: 'Departments', icon: 'bi:person-fill', link: '/admin/departments' },
  { id: 6, title: 'Employees', icon:'bi:person-fill', link: '/admin/employees' },
  { id: 7, title: 'Accounts', icon:'bi:person-fill', link: '/admin/accounts' },
  { id: 8, title: 'Payroll', icon: 'bi:person-fill', link:  '/admin/payroll' },
  { id: 9, title: 'Chats', icon: 'bi:person-fill', link:  '/admin/chats' },
  { id: 10, title: 'Calls', icon: 'bi:person-fill', link:  '/admin/calls' },
  { id: 11, title: 'Email', icon: 'bi:person-fill', link:  '/admin/emails' },
  { id: 12, title: 'Blog', icon: 'bi:person-fill', link:  '/admin/blog' },
  { id: 13, title: 'Assets', icon: 'bi:person-fill', link:  '/admin/assets' },
  { id: 14, title: 'Logout', icon: 'bi:person-fill', link:  '/admin/logout' },

]
</script>