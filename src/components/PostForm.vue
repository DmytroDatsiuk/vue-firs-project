<template>
  <form class="form" @submit.prevent>
    <h4>Створення поста</h4>
    <my-input v-model="post.title" type="text" placeholder="Назва" />
    <my-input v-model="post.body" type="text" placeholder="Опис" />
    <my-button class="btn" style="margin-top: 15px" @click="createPost"
      >Створити</my-button
    >
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
    createPost(event) {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
}
</style>
