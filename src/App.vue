<script setup>
import { onMounted, onUnmounted, ref } from "vue";

const name = ref("mike");

const changeName = () => {
  name.value = "Jacky";
  console.log(name);
};

onMounted(() => {
  console.log(name.value);
});

// vue2 destroy 改成 unmounted
onUnmounted(() => {});
</script>

<template>
  <div>
    <h1>{{ name }}</h1>
    <button @click="changeName">click</button>
  </div>
</template>

<style></style>
