<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Ref</h2>
    <p>{{ userOne.name}} - {{ userOne.age }}</p>
    <button @click="updateUserOne">Update User One</button>
    <h2>Reactive</h2>
    <p>{{ userTwo.name}} - {{ userTwo.age }}</p>
    <button @click="updateUserTwo">Update User Two</button>
  </div>
</template>

<script>
import { ref, reactive } from '@vue/reactivity';
// @ is an alias to /src

export default {
  name: 'Home',
  setup() {
    const userOne = ref({ name: 'Carl', age: 20 });
    const userTwo = reactive({ name: 'Karl', age: 25 });

    const updateUserOne = () => {
      userOne.value.age = 25;
    }

    const updateUserTwo = () => {
      userTwo.age = 30;
    }

    return { userOne, userTwo, updateUserOne, updateUserTwo }
  }
}
</script>
