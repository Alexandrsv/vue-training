<template>
  <div class="app">
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <input
        type="text"
        v-bind:value="title"
        @input="title = $event.target.value"
        class="input"
        placeholder="Название поста"
      />
      <input
        type="text"
        v-bind:value="body"
        @input="body = $event.target.value"
        class="input"
        placeholder="Содержание поста"
      />
      <button class="btn" @click="createPost">Создать</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Содержание: </strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Пост о JS",
          body: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. A at, commodi deserunt ea, fugit ipsa, laudantium maiores molestias perspiciatis porro quibusdam quo sequi voluptatum! Earum, id, soluta! A, eaque, quidem.",
        },
        {
          id: 2,
          title: "Пост о " + Math.floor(Math.random() * 100),
          body: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. A at, commodi deserunt ea, fugit ipsa, laudantium maiores molestias perspiciatis porro quibusdam quo sequi voluptatum! Earum, id, soluta! A, eaque, quidem.",
        },
        {
          id: 3,
          title: "Пост о " + Math.floor(Math.random() * 100),
          body: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. A at, commodi deserunt ea, fugit ipsa, laudantium maiores molestias perspiciatis porro quibusdam quo sequi voluptatum! Earum, id, soluta! A, eaque, quidem.",
        },
      ],
      title: "",
      body: "",
    };
  },
  methods: {
    createPost() {
      this.posts.push({
        id: this.posts.length + 1,
        title: this.title,
        body: this.body,
      });

      this.title = "";
      this.body = "";
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.app {
  padding: 20px;
}

form {
}

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

.post {
  padding: 15px;
  border: 1px solid teal;
  margin-top: 15px;
}
</style>
