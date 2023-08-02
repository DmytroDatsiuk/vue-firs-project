<template>
  <div class="app">
    <h1>Сторінка з постами</h1>
    <my-button @click="fetchPosts">Отримати пости</my-button>
    <my-button @click="showDialog" style="margin: 15px 0">
      Створити пост
    </my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost" />
    </my-dialog>
    <post-list :posts="posts" @remove="removePost" />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
import axios from "axios";

export default {
  components: {
    PostForm,
    PostList,
  },

  data() {
    return {
      posts: [
        { id: 1, title: "JavaScript", body: "Опис поста" },
        { id: 2, title: "JavaScript 2", body: "Опис поста 2" },
        { id: 3, title: "JavaScript 3", body: "Опис поста 3" },
        { id: 4, title: "JavaScript 4", body: "Опис поста 4" },
      ],
      dialogVisible: false,
    };
  },
  methods: {
    createPost(post) {
      const title = post.title.trim();
      const body = post.body.trim();

      if (title === "" || body === "") {
        return;
      }

      this.posts.push(post);
      this.dialogVisible = false;
    },

    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id);
    },
    showDialog() {
      this.dialogVisible = true;
    },
    async fetchPosts() {
      try {
        const response = await axios.get(
          "https://jsonplaceholder.typicode.com/posts?_limit=10"
        );
        console.log(response);
      } catch (e) {
        console.log(e);
      }
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>
