
<template>
<div>
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
</template>

<script setup>
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



</script>

