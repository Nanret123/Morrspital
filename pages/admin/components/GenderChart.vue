<template>
    <div class="p-4 w-[350px] bg-white shadow-lg rounded-lg">
      <div class="flex justify-between items-center mb-4">
        <div>Gender Analytics</div>
        <div>Pie Chart icon</div>
      </div>
      <!-- Set appropriate width and height using TailwindCSS -->
      <canvas id="pie-canvas" class="h-40 w-40"></canvas>
    </div>
  </template>
  
  <script setup>
  import { onMounted } from 'vue'
  import { Chart } from 'chart.js/auto'
  
  // Mock gender data (e.g., Male vs Female)
  const chartData = {
    labels: ['Male', 'Female', 'Children'],
    datasets: [
      {
        label: 'Gender Distribution',
        backgroundColor: ['#42A5F5', '#FF6384', '#b4eb34'], // Colors for the pie chart
        data: [50, 30, 20] // Example data (60% male, 40% female)
      }
    ]
  }
  
  // Chart options
  const options = {
    responsive: true,
    plugins: {
      legend: {
        position: 'bottom' // Position of the legend
      }
    }
  }
  
  // Render the chart after the component mounts
  onMounted(async () => {
    // Get the 2D rendering context of the canvas
    const ctx = document.getElementById('pie-canvas').getContext('2d')
  
    if (ctx) {
      new Chart(ctx, {
        type: 'pie', // Use 'pie' type for a pie chart
        data: chartData,
        options
      })
    }
  })
  </script>
  