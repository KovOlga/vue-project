<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  emits: ['create'],
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    }
  }
}
</script>
<template>
  <form class="form" @submit.prevent>
    <h4>Create a post</h4>
    <input v-model="post.title" class="input" type="text" placeholder="Title" />
    <input
      v-bind:value="post.body"
      @input="post.body = $event.target.value"
      class="input"
      type="text"
      placeholder="Body"
    />
    <button class="button" @click="createPost">Create</button>
  </form>
</template>
<style scoped>
.form {
  display: flex;
  flex-direction: column;
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
