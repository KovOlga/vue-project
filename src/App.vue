<script setup lang="ts">
// import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue'
const posts = ref([
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
])
const title = ref('')
const body = ref('')

const createPost = () => {
  const newPost = {
    id: Date.now(),
    title: title.value,
    body: body.value
  }
  console.log('dd', newPost)
  posts.value.push(newPost)
  console.log('posts', posts)
  title.value = ''
  body.value = ''
}

console.log('cdfcvd', posts.value)
</script>

<template>
  <div class="app">
    <form class="form" @submit.prevent>
      <h4>Create a post</h4>
      <input
        v-bind:value="title"
        @input="title = $event.target.value"
        class="input"
        type="text"
        placeholder="Title"
      />
      <input
        v-bind:value="body"
        @input="body = $event.target.value"
        class="input"
        type="text"
        placeholder="Body"
      />
      <button class="button" @click="createPost">Create</button>
    </form>
    <div class="post" v-for="post in posts" v-bind:key="post.id">
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Описание: </strong>{{ post.body }}</div>
    </div>
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

.form {
  display: flex;
  flex-direction: column;
}

.post {
  margin-top: 15px;
  padding: 15px;
  border: 1px solid teal;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.button {
  align-self: flex-end;
  margin-top: 15px;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>
