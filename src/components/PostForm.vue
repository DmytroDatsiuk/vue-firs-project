<template>
  <form class="form" @submit.prevent>
    <h4>Створення поста</h4>
    <input v-model="post.title" class="input" type="text" placeholder="Назва" />
    <input v-model="post.body" class="input" type="text" placeholder="Опис" />
    <my-button class="btn" style="margin-top: 15px" @click="createPost"
      >Створити</my-button
    >
  </form>
</template>

<script>
import MyButton from "../components/UI/MyButton";

export default {
  components: {
    MyButton,
  },
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

.input {
  width: 100%;
  border: 2px solid skyblue;
  border-radius: 5px;
  padding: 10px 15px;
  margin-top: 15px;
}
</style>
