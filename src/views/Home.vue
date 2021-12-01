<template>
  <div class="home">
    home
    <p ref="par">My name is {{ name }} and my age is {{ age }}.</p>
    <button @click="handleclick">click me</button>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
// @ is an alias to /src

export default {
  name: 'Home',
  setup() {
    let name = 'Carl';
    let age = 20;

    let par = ref(null);

    let handleclick = () => {
      console.log(par.value);
      par.value.classList.add('test');
      par.value.textContent = 'hello world!';
    }

    return { name, age, handleclick, par }
  }
}
</script>
