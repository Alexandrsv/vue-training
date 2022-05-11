<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {
  components: {
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
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
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
