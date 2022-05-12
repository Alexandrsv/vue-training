<template>
  <button class="btn"><slot></slot></button>
</template>

<script>
export default {
  name: "my-btn",
};
</script>

<style scoped>
.btn {
  padding: 10px;
  border: none;
  border-radius: 5px;
  background-color: teal;
  color: #fff;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
}
</style>
