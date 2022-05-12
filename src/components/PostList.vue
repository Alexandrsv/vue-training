<template>
  <div class="post_list" v-if="posts.length > 0">
    <h3 style="padding-top: 10px">Список записей</h3>
    <post-item
      v-for="post in posts"
      :post="post"
      :key="post.id"
      @remove="$emit('remove', post)"
    />
  </div>
  <h3 v-else style="color: teal; margin-top: 25px">
    Список записей пуст, их больше нет
  </h3>
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
