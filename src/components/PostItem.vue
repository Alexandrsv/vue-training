<template>
  <div class="post">
    <div><strong>Название: </strong>{{ post.title }}</div>
    <div><strong>Содержание: </strong>{{ post.body }}</div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  padding: 15px;
  border: 1px solid teal;
  margin-top: 15px;
}
</style>
