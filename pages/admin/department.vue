<script setup>
const list = [
  { id: 1, serialNumber: '01', name: 'Cardiology', status: 'Active' },
  { id: 2, serialNumber: '02', name: 'Cardiology', status: 'Inactive' },
  { id: 3, serialNumber: '03', name: 'Cardiology', status: 'Active' },
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
            <span class="text-2xl font-bold mb-6">Departments</span>
          </div>
          <button type="submit"
            class="h-10 w-32 text-sm font-medium text-white bg-blue-500 rounded-lg hover:bg-blue-600 focus:outline-none focus:shadow-outline">
            Add Department
          </button>
        </div>
        <div>
          <div class="flex justify-between px-[30px]">
            <span>Department List</span>
            <span>View All
              <Icon name="ant-design:right-outlined" />
            </span>
          </div>
          <table class="min-w-full border-2 border-solid border-gray-300 mt-7">
            <thead>
              <tr>
                <th class="table-header">Serial Number</th>
                <th class="table-header">Department Name</th>
                <th class="table-header">Status</th>
                <th class="table-header">Action</th>
              </tr>
            </thead>
            <tbody v-for="(item, index) in list" :key="item.id" class="border-spacing-4">
              <tr>
                <td class="table-cell">{{ item.serialNumber }}</td>
                <td class="table-cell">{{ item.name }}</td>
                <td class="table-cell">{{ item.status }}</td>
                <td class="table-cell">
                  <button class="mr-2">
                    <Icon name="ant-design:edit-outlined" />
                  </button>
                  <button>
                    <Icon name="bx:trash" style="color:red" />
                  </button>
                </td>
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