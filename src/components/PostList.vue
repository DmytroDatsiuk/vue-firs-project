<template>
  <div>
    <h3>Список користувачів</h3>
    <post-item v-for="post in posts" v-bind:post="post" />
  </div>
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
