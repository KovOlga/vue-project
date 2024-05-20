<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>
<template>
  <div class="post" v-for="post in posts" v-bind:key="post.id">
    <div><strong>Название: </strong>{{ post.title }}</div>
    <div><strong>Описание: </strong>{{ post.body }}</div>
  </div>
</template>
<style>
.post {
  margin-top: 15px;
  padding: 15px;
  border: 1px solid teal;
}
</style>
