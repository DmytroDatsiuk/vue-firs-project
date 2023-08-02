<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-button",
};
</script>

<style scoped>
.btn {
  align-self: flex-end;
  padding: 10px 15px;
  background-color: aqua;
  color: teal;
  border: 1px solid teal;
  border-radius: 5px;
  font-weight: 900;
}
</style>
