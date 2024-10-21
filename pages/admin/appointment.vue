<script setup>
import SideMenu from './components/SideMenu.vue';
import SearchBar from './components/SearchBar.vue';

const items = [
  { id: 1, name: 'Victor Mike', profession: 'Cardiologist', image: '/images/spongebob.png' },
  { id: 2, name: 'Stephen Balogun', profession: 'Dentist', image: '/images/spongebob.png' },
  { id: 3, name: 'Scarlet Witch', profession: 'Ophthalmologist', image: '/images/spongebob.png' },

]

const notifications = [
  { id: 1, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male', status: 'confirmed' },
  { id: 2, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male', status: 'rejected' },
  { id: 3, name: 'Victor Mike', age: 23, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male', status: 'confirmed' },
  { id: 4, name: 'Victor Mike', age: 34, dateTime: '12 April 9:30', image: '/images/spongebob.png', gender: 'male', status: 'pending' }
];

const appointments = [
  { id: 1, name: 'Victor Mike', date: '12 April', time: '12:00pm', image: '/images/spongebob.png', status: 'confirmed', comment: 'This was pretty nice' },
  { id: 2, name: 'Victor Mike', date: '12 April', time: '12:00pm', image: '/images/spongebob.png', status: 'confirmed', comment: 'This was pretty nice' },
  { id: 3, name: 'Victor Mike', date: '12 April', time: '12:00pm', image: '/images/spongebob.png', status: 'confirmed', comment: 'This was pretty nice' },
];
</script>

<template>
  <div class="flex">
    <SideMenu />
    <div class="flex flex-col flex-1 w-full h-full">
      <SearchBar />
      <div class=" h-full p-[30px]">
        <div class="flex justify-between">
          <div>
            <h1>Welcome Mr. Victor</h1>
            <p>Have a nice day at work</p>
          </div>
          <button class="bg-sky-950 p-3 rounded-md">Book an appointment</button>
        </div>
      </div>
      <div class="flex flex-wrap mt-4 gap-2 w-full px-5">
        <div class="flex-1">
          <div class="flex justify-between">
            <p>Doctors List</p>
            <p>View All</p>
          </div>
          <div class="flex gap-6" v-for="(item, index) in items" :key="index.id">
            <img :src="item.image" class="rounded-full h-[50px] w-[50px] object-cover m-2" />
            <div>
              <h3>{{ item.name }}</h3>
              <p>{{ item.profession }}</p>
            </div>
          </div>
        </div>
        <div class="flex-1">
          <div class="flex justify-between">
            <p>Appointment List</p>
            <p>View All</p>
          </div>
          <div v-for="(item, index) in notifications" :key="item.id" class="flex justify-between items-center m-2">
            <img :src="item.image" alt="Profile Picture" class="w-[50px] h-[50px] rounded-full object-cover" />

            <div class="">
              <h3>{{ item.name }}</h3>
              <p>Age: {{ item.age }}</p>
              <p>Date: {{ item.dateTime }}</p>
            </div>

            <div>
              <Icon :name="'material-symbols:notifications-sharp'" :class="[
                item.status === 'confirmed' ? 'text-green-500' : '',
                item.status === 'rejected' ? 'text-red-500' : '',
                item.status === 'pending' ? 'text-yellow-500' : ''
              ]" />
            </div>
          </div>
        </div>
        <div class="flex-1">
          <div class="flex justify-between">
            <p>Create Appointment</p>
            <p>View All</p>
          </div>
          <div>
            <p>Thursday, 4th March, 2024</p>
            <p>10:00am - 10:30am(30min)</p>
            <div class="flex">
              <img src="/images/spongebob.png" class="rounded-full h-[50px] w-[50px] object-cover m-2" />
              <h3>Mr. Victor</h3>
            </div>
            <div class="flex gap-2">
              <button
                class="px-[30px] py-3 border-4 border-solid border-[bg-purple-800] flex-1 rounded-md text-purple-800">Reschedule</button>
              <button class="px-[30px] py-3 flex-1 bg-purple-800 rounded-md">View Details</button>
            </div>
          </div>
        </div>
      </div>
      <div class="px-5 overflow-x-auto" >
        <table class="min-w-full border-2 border-solid border-gray-300">
          <thead>
            <tr>
              <th class="table-header">Doctor's Name</th>
              <th class="table-header">Id</th>
              <th class="table-header">Date</th>
              <th class="table-header">Time</th>
              <th class="table-header">Comments</th>
              <th class="table-header">Status</th>
            </tr>
          </thead>
          <tbody v-for="(item, index) in appointments" :key="item.id" class="border-spacing-4">
            <tr>
              <td class="table-cell">
                <div class="flex items-center gap-2">
                  <img :src="item.image" alt="Profile Picture" class="w-[50px] h-[50px] rounded-full object-cover" />
                  {{ item.name }}
                </div>
                </td>
              <td class="table-cell">{{ item.id }}</td>
              <td class="table-cell">{{ item.date }}</td>
              <td class="table-cell">{{ item.time }}</td>
              <td class="table-cell">{{ item.comment }}</td>
              <td class="table-cell">{{ item.status }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<style scoped>
.table-header {
  @apply py-3 px-6 border-b ; /* Applies padding and border for header */
}

.table-cell {
  @apply py-3 px-6 border-b text-center my-2.5; /* Applies padding and border for cells */
}
</style>