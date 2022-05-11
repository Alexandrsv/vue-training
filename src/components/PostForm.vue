<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <input
      type="text"
      v-model="post.title"
      class="input"
      placeholder="Название поста"
    />
    <input
      type="text"
      v-model="post.body"
      class="input"
      placeholder="Содержание поста"
    />
    <button class="btn" @click="createPost">Создать</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);

      this.post = { title: "", body: "" };
    },
  },
};
</script>

<style scoped>
.btn {
  margin-bottom: 20px;
  padding: 10px;
  border: none;
  border-radius: 5px;
  background-color: teal;
  color: #fff;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  justify-self: flex-start;
}

.input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  margin-bottom: 10px;
  outline: none;
}
</style>
