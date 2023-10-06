<script setup>
import axios from "axios"


// Récup data de l API

const response = await axios.get("https://rickandmortyapi.com/api/character?limit=8")
console.log(response.data.length)
</script>

<template>
    <div>
        
        <h1>Rick and Morty</h1>
        <h2>{{ response.data.length }}</h2>
    </div>
</template>