<template>
    <div class="card">
<h2>
    {{ props.pokemon[0]}}
</h2>
<p>Shootings there: {{ props.pokemon[1] }}</p>
</div>
</template>
<script setup>
import {computed} from 'vue'
const props = defineProps({
    pokemon: Object,
    id: Number
})

</script>


<style scoped>
.card {
    width: 28%;
    height: 500px;
    background-color: navy;
    margin: 30px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px;
    text-transform: uppercase;
    color: aliceblue;
}
img{
    width: 100%;
    height: 80%;
    object-fit: cover;
}
</style>
