<template>
    <!-- <div class="home">
      <h1>This is a home page</h1>
      <PokemonCard
      v-for="(monster, index) in pokemon"
      :key="monster.name"
      :id="index + 1"
      :pokemon="monster"
      />
    </div> -->
  </template>
  
  <style>
  @media (min-width: 1024px) {
    .home {
      min-height: 100vh;
      display: flex;
      align-items: center;
    }
  }
  </style>
  