<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Computed</h2>
    <!-- <p>{{ name}}</p> -->
    <input type="text" v-model="search" id="">
    <p>Search term: {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
    <button @click="handleclick">Stop Watch</button>
  </div>
</template>

<script>
import { computed, ref } from '@vue/reactivity';
import { watch, watchEffect } from '@vue/runtime-core';
// @ is an alias to /src

export default {
  name: 'Home',
  setup() {
    const search = ref('');
    const names = ref(['Karl', 'Carl', 'Callis']);

    const stopWatch = watch(search, () => {
      console.log('watching search');
    })
    
    const stopEffect = watchEffect(() => {
      console.log('watchEffect search', search.value);
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.toLowerCase().includes(search.value));
    })

    const handleclick = () => {
      stopWatch();
      stopEffect();
    }

    return { names, search, matchingNames, stopWatch, stopEffect, handleclick }
  }
}
</script>
