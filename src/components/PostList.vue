<template>
  <div v-if="posts.length > 0">
    <h3>Список користувачів</h3>
    <post-item
      v-for="post in posts"
      v-bind:post="post"
      :key="post.id"
      @remove="$emit('remove', post)"
    />
  </div>
  <h2 v-else style="color: red">Список постів пустий</h2>
</template>

<script>
import PostItem from "@/components/PostItem.vue";
export default {
  components: { PostItem },
  props: {
    posts: { type: Array, required: true },
  },
};
</script>

<style scoped></style>
