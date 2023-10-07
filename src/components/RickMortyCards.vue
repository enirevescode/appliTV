<script setup>
import axios from "axios"
import {ref, watch} from "vue"

//stockage du state
const characters = ref(null)

//pagination
const page = ref(0)

// Récup data de l API + limitation à 8 du nbre de cards/page
const response = await axios.get("https://rickandmortyapi.com/api/character?limit=8")
characters.value = response.data
console.log ("characters.value",characters.value.results)
console.log( "type de data",typeof response)
console.log( " length",response.data.length)


//Mise en marche des btn "next" et "back"
watch(page, async () =>{
    const res = await axios.get(`https://rickandmortyapi.com/api/character?limit=8&offset=${page.value*8}`)
    characters.value = res.data
})


</script>

<template>
    <div>
        
        <h1>Rick and Morty</h1>
        <h2>{{ characters }}</h2>
        <button @click="page++">Next</button>
        <button @click="page--">Back</button>
    </div>
</template>