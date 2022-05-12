<template>
  <form @submit.prevent>
    <h4 style="margin-bottom: 10px">Создание поста</h4>
    <my-input type="text" v-model="post.title" placeholder="Название поста" />
    <my-input type="text" v-model="post.body" placeholder="Содержание поста" />
    <my-btn class="btn" @click="createPost">Создать</my-btn>
  </form>
</template>

<script>
import MyInput from "@/components/UI/MyInput";
export default {
  components: { MyInput },
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

<style scoped></style>
