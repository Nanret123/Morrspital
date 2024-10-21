<script setup>
const list = [
  { id: 1, name: 'Victor Mike', age: 12, doctorName: 'Nick Jones', department: 'Pharmacy', date: '12 April', gender: 'male', role: 'Employee', image: '/images/spongebob.png', status: 'Active' },
  { id: 2, name: 'Victor Mike', age: 12, doctorName: 'Nick Jones', department: 'Pharmacy', date: '12 April', gender: 'male', role: 'Employee', image: '/images/spongebob.png', status: 'Inactive' },
  { id: 3, name: 'Victor Mike', age: 12, doctorName: 'Nick Jones', department: 'Pharmacy', date: '12 April', gender: 'male', role: 'Employee', image: '/images/spongebob.png', status: 'Active' },
];
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
            <span class="text-2xl font-bold mb-6">Appointments</span>
          </div>
          <button type="submit"
            class="h-10 w-32 text-sm font-medium text-white bg-blue-500 rounded-lg hover:bg-blue-600 focus:outline-none focus:shadow-outline">
            Add Appointments
          </button>
        </div>
        <div>
          <div class="flex justify-between px-[30px]">
            <span>Appointment List</span>
            <span>View All
              <Icon name="ant-design:right-outlined" />
            </span>
          </div>
          <table class="min-w-full border-2 border-solid border-gray-300 mt-7">
            <thead>
              <tr>
                <th class="table-header">AppointmentId</th>
                <th class="table-header">Patient Name</th>
                <th class="table-header">Age</th>
                <th class="table-header">Doctor Name</th>
                <th class="table-header">Department</th>
                <th class="table-header">Appointment Date</th>
                <th class="table-header">Status</th>
              </tr>
            </thead>
            <tbody v-for="(item, index) in list" :key="item.id" class="border-spacing-4">
              <tr>
                <td class="table-cell">{{ item.id }}</td>
                <td class="table-cell">
                  <div class="flex items-center gap-2">
                    <img :src="item.image" alt="Profile Picture" class="w-[50px] h-[50px] rounded-full object-cover" />
                    {{ item.name }}
                  </div>
                </td>
                <td class="table-cell">{{ item.age }}</td>
                <td class="table-cell">{{ item.doctorName }}</td>
                <td class="table-cell">{{ item.department }}</td>
                <td class="table-cell">{{ item.date }}</td>
                <td class="table-cell">{{ item.status }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.table-header {
  @apply py-3 px-6 border-b;
  /* Applies padding and border for header */
}

.table-cell {
  @apply py-3 px-6 border-b text-center my-2.5;
  /* Applies padding and border for cells */
}
</style>