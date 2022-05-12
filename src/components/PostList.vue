<template>
  <div class="post_list">
    <h3>Список записей</h3>
    <post-item v-for="post in posts" :post="post" />
  </div>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.post_list {
  margin-top: 15px;
}
</style>
