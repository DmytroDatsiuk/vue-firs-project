<template>
  <div class="navbar">
    <div @click="$router.push('/')">Vue 3</div>
    <div class="navbar__btns">
      <my-button @click="$router.push('/posts')" style="margin-left: 20px"
        >Пости</my-button
      >
      <my-button @click="$router.push('/about')" style="margin-left: 20px"
        >Про сайт</my-button
      >
      <my-button @click="$router.push('/store')" style="margin-left: 20px"
        >Store</my-button
      >
      <my-button @click="$router.push('/composition')" style="margin-left: 20px"
        >Composition</my-button
      >
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.navbar {
  height: 50px;
  background-color: #6d8d84;
  box-shadow: 2px 2px 4px gray;
  display: flex;
  align-items: center;
  padding: 0 15px;
}

.navbar__btns {
  margin-left: auto;
}
</style>
