
<template>
  <div class="container">
    <h3> NYPD Shooting Incident Data (Year To Date) </h3>
    <BarChart></BarChart>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import BarChart from '../components/BarChart.vue'
const incidents = ref('')
async function getIncidents() {
  let res = await fetch('https://data.cityofnewyork.us/resource/5ucz-vwe8.json')
  let data = await res.json()
  console.log(data)
}
onMounted(async () => {
  await getIncidents()
})
</script>
<style scoped>
.container {
  width: 60vw;
  margin: 20px auto;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  flex-direction: row;
  align-items: center;
  justify-content: space around;
}
</style>
