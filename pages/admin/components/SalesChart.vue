<template>
  <div class="p-4 w-[350px] bg-white shadow-lg rounded-lg">
    <div class="flex justify-between items-center mb-4">
      <div>Total Sales $234</div>
      <div>Graph icon</div>
    </div>
    <!-- Set appropriate width and height using TailwindCSS -->
    <canvas id="canvas" class="h-96"></canvas>
  </div>
</template>

<script setup>
import { onMounted } from 'vue'
import { Chart } from 'chart.js/auto'

// Mock sales data for 12 months
const chartData = {
  labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
  datasets: [
    {
      label: 'Sales',
      backgroundColor: '#42A5F5',
      data: [50, 70, 30, 100, 80, 120, 140, 130, 90, 150, 160, 180]
    }
  ]
}

// Chart options
const options = {
  scales: {
    y: {
      beginAtZero: true
    }
  }
}

// Render the chart after the component mounts
onMounted(async () => {
  // Get the 2D rendering context of the canvas
  const ctx = document.getElementById('canvas').getContext('2d')

  if (ctx) {
    new Chart(ctx, {
      type: 'bar',
      data: chartData,
      options
    })
  }
})
</script>