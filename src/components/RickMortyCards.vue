<script setup>
import axios from "axios"

// Récup data de l API
const response = axios.get("https://rickandmortyapi.com/api/character")
console.log(response)
</script>

<template>
    <div>
        <h1>Rick and Morty</h1>
    </div>
</template>