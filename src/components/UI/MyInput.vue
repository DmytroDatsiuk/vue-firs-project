<template>
  <input class="input" type="text" :value="modelValue" @input="updateInput" />
</template>

<script>
export default {
  name: "my-input",
  props: {
    modelValue: [String, Number],
  },
  methods: {
    updateInput(e) {
      this.$emit("update:modelValue", e.target.value);
    },
  },
};
</script>

<style scoped>
.input {
  width: 100%;
  border: 2px solid skyblue;
  border-radius: 5px;
  padding: 10px 15px;
  margin-top: 15px;
}
</style>
