<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Props</h2>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostList from "@/components/PostList.vue";
import { ref } from '@vue/reactivity';
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    PostList
  },
  setup() {
    const posts = ref([
      {title: 'Welcome home to vue', body: 'Non minim nostrud duis veniam fugiat dolore occaecat eu. Cillum culpa irure elit excepteur minim. Est culpa reprehenderit anim ad aliquip nisi ea laboris aute aliqua culpa exercitation exercitation veniam.', id: 1},
      {title: 'Enjoy coding in vue', body: 'Irure exercitation dolor mollit aliqua. Reprehenderit fugiat ex fugiat amet velit magna sunt velit commodo aliquip sit elit excepteur consequat. Ex duis eiusmod id amet incididunt qui Lorem exercitation duis ex eu qui consectetur. Enim aliqua veniam labore anim laboris in esse pariatur.', id: 2}
    ]);
    

    return { posts }
  }
}
</script>
