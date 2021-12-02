<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Props</h2>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>Loading . . .</div>
  </div>
</template>

<script>
import PostList from "@/components/PostList.vue";
import getPosts from "@/composables/getPosts";
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    PostList
  },
  setup() {
    const { posts, error, load } = getPosts();

    load();

    return { posts, error }
  }
}
</script>
