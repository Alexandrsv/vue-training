<template>
  <input :value="modelValue" @input="updateInput" class="input" type="text" />
</template>

<script>
export default {
  name: "my-input",
  props: {
    modelValue: {
      type: [String, Number],
    },
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
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  margin-bottom: 10px;
  outline: none;
}
</style>
