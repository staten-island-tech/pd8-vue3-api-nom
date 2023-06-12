<script setup>
    let prop = defineProps({data:Array})
    let boros = prop.data.map(d=>d[0])
    let count = prop.data.map(d=>d[1])
    import { registerables } from  "chart.js"
    import Chart from 'chart.js/auto';

 function mounted() {
    const ctx = document.getElementById('sillyGoose');
    new Chart(ctx, {
  type: 'pie',
  data: {
    labels: boros,
    datasets: [{
      label: '# of Votes',
      data: count,
      backgroundColor: [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
    ],
    }]
  },
});
Chart.register(...registerables)
}
setTimeout(mounted,1000)
</script>

<template>
<canvas id="sillyGoose"></canvas>
</template>

<style scoped>
canvas{
    width: 50vw;
}
</style>