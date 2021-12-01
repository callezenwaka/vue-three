<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Computed</h2>
    <!-- <p>{{ name}}</p> -->
    <input type="text" v-model="search" id="">
    <p>Search term: {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  </div>
</template>

<script>
import { ref, computed } from '@vue/reactivity';
// @ is an alias to /src

export default {
  name: 'Home',
  setup() {
    // const name = computed(() => {
    //   return 'Karl';
    // })
    const search = ref('');
    const names = ref(['Karl', 'Carl', 'Callis'])

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.toLowerCase().includes(search.value));
    })

    return { names, search, matchingNames }
  }
}
</script>
