<script setup>
    let prop = defineProps({data:Array})
    let boros = prop.data.map(d=>d[0])
    let count = prop.data.map(d=>d[1])
    import { registerables } from  "chart.js"
    import Chart from 'chart.js/auto';

 function mounted() {
    const ctx = document.getElementById('myChart');
    new Chart(ctx, {
  type: 'bar',
  data: {
    labels: boros,
    datasets: [{
      label: '# of Shootings',
      data: count,
      borderWidth: 1
    }]
  },
  options: {
    scales: {
      y: {
        beginAtZero: true
      }
    }
  }
});
Chart.register(...registerables)
}
setTimeout(mounted,1000)
</script>

<template>
    <div>
<canvas id="myChart"></canvas>
</div>
</template>

<style scoped>
canvas{
    width: 50vw;
}
</style>