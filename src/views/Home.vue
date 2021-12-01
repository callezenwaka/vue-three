<template>
  <div class="home">
    home
    <p>My name is {{ name }} and my age is {{ age }}.</p>
    <button @click="handleclick">click me</button>
    <button @click="age++">Increase Age by 1</button>
    <input type="text" v-model="name" id="">
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
// @ is an alias to /src

export default {
  name: 'Home',
  setup() {
    let name = ref('Carl');
    let age = ref(20);

    let handleclick = () => {
      name.value = 'Karl';
      age.value = 25;
    }

    return { name, age, handleclick }
  }
}
</script>
