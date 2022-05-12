<template>
  <div class="app">
    <h1 style="margin-bottom: 20px">Страница с постами</h1>
    <my-btn @click="showDialog">Созадить пост</my-btn>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost" />
    </my-dialog>
    <post-list :posts="posts" @remove="removePost" />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
import MyBtn from "@/components/UI/MyBtn";

export default {
  components: {
    MyBtn,
    PostForm,
    PostList,
  },
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
      dialogVisible: false,
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id);
    },
    showDialog() {
      this.dialogVisible = true;
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
</style>
