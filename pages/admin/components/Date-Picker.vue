<template>
    <div>
      <date-picker v-model="selectedDate"></date-picker>
    </div>
  </template>
  
  <script>
  import DatePicker from 'vue-datepicker';
  
  export default {
    components: {
      DatePicker,
    },
    data() {
      return {
        selectedDate: null, // Initialize with null or your default date
      };
    },
  };
  </script>
  