<script setup>
import RickMortyCards from './components/RickMortyCards.vue';

</script>

<template>
 <main>
<h1>HERO</h1>
<Suspense>
   <template #default>
      <RickMortyCards/>
   </template>
   <template #fallback>
      <p>Loading ...</p>
   </template>

 </Suspense>
 </main>
 

</template>

