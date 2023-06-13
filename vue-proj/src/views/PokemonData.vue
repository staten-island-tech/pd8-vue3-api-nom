<template>
    <div class="container">
        <PokemonCard v-for="(monster, index) in pokemon"
        :key="monster.name"
        :id="index + 1"
        :pokemon="monster"
        />
    </div>
    <barChart v-if="pokemon" :data="pokemon"></barChart>
    <pieChart v-if="pokemon" :data="pokemon"></pieChart>

    </template>
    
    
    <script setup>
    import {ref, onMounted} from 'vue'
    import barChart from '../components/barChart.vue';
    import pieChart from '../components/pieChart.vue';

    import PokemonCard from '../components/PokemonCard.vue'
    const pokemon = ref(false)
    async function getPokemon() {
        let res = await fetch('https://data.cityofnewyork.us/resource/5ucz-vwe8.json')
    let data = await res.json()
    let newData = [
        ["Manhatan",data.filter(sh=>sh.boro=="MANHATTAN").length],
        ["Staten Island",data.filter(sh=>sh.boro=="STATEN ISLAND").length],
        ["Bronx",data.filter(sh=>sh.boro=="BRONX").length],
        ["Brooklyn",data.filter(sh=>sh.boro=="BROOKLYN").length],
        ["Queens",data.filter(sh=>sh.boro=="QUEENS").length],
    ]
    console.log(newData)
    pokemon.value = newData
    }
    onMounted(() => {
        getPokemon()
    })
    </script>
    <style scoped>
    .container {
        width: 80vw;
        margin: 30px auto;
        display: flex;
        flex-wrap: wrap;
        flex-direction: row;
        align-items: center;
        justify-content: space-around;
    }
    </style>