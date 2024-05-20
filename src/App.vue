<script lang="ts">
import PostForm from '@/components/post-form.vue'
import PostList from '@/components/post-list.vue'
export default {
  components: {
    PostList,
    PostForm
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: 'JS1',
          body: 'Description'
        },
        {
          id: 2,
          title: 'JS2',
          body: 'Description'
        },
        {
          id: 3,
          title: 'JS3',
          body: 'Description'
        },
        {
          id: 4,
          title: 'JS4',
          body: 'Description'
        }
      ]
    }
  },
  methods: {
    createPost(post: any) {
      this.posts.push(post)
    }
  }
}
</script>

<template>
  <div class="app">
    <PostForm @create="createPost" />
    <PostList v-bind:posts="posts" />
    <!-- <PostList :posts /> the same -->
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>
