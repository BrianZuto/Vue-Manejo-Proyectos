<script setup>
import { onMounted, ref, reactive, defineProps } from "vue";

const text = ref("");
const emits = defineEmits(["onNewItem"]);

function handleKeyDown(evt) {
  if (evt.key === "Enter") {
    emits("onNewItem", text);
    text.value = "";
  }
}
</script>

<template><input v-model="text" @keydown="handleKeyDown" /></template>

<style scoped></style>