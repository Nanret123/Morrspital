<script setup>
import SideMenu from './components/SideMenu.vue';
import SearchBar from './components/SearchBar.vue';
</script>

<template>
  <div class="flex">
    <SideMenu />
    <div class="flex flex-col flex-1 w-full h-full">
      <SearchBar />
      <div class="bg-slate-400 h-full p-[30px]">
        <h1 class="text-2xl font-bold mb-6">Add New Schedule</h1>
        <form>
          <div class="flex flex-wrap gap-4">
            <div class="flex-1">
              <label class="block text-gray-700 text-sm font-bold mb-2" for="patient_name">
                Doctor Name
              </label>
              <input id="patient_name" type="text"
                class="w-full px-3 py-3 text-gray-700 bg-white rounded-lg focus:outline-none focus:shadow-outline"
                required />
            </div>
            <div class="flex-1">
              <label class="block text-gray-700 text-sm font-bold mb-2" for="doctor_name">
                Available Days
              </label>
              <input id="doctor_name" type="text"
                class="w-full px-3 py-3 text-gray-700 bg-white rounded-lg focus:outline-none focus:shadow-outline"
                required />
            </div>
          </div>
          <div class="flex flex-wrap gap-4 mt-5">
            <div class="flex-1">
              <label class="block text-gray-700 text-sm font-bold mb-2" for="date">
                Start Time
              </label>
              <input id="date" type="time"
                class="w-full px-3 py-3 text-gray-700 bg-white rounded-lg focus:outline-none focus:shadow-outline"
                required />
            </div>
            <div class="flex-1">
              <label class="block text-gray-700 text-sm font-bold mb-2" for="time">
                End Time
              </label>
              <input id="time" type="time"
                class="w-full px-3 py-3 text-gray-700 bg-white rounded-lg focus:outline-none focus:shadow-outline"
                required />
            </div>
          </div>
          <div class="mt-5">
            <button type="submit"
              class="w-full px-4 py-3 text-sm font-medium text-white bg-blue-500 rounded-lg hover:bg-blue-600 focus:outline-none focus:shadow-outline">
              Add Schedule
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>