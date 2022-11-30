<script setup>
// setup 這是個語法糖,可以和App2.vue比較
import { onMounted, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";

const props = defineProps({
  data: {
    type: Object,
    default: () => ({}),
  },
});
const count = ref(0);
const increment = () => {
  count.value += 1;
  // props 使用
  // props.num 之類
};

onMounted(() => {
  console.log(count.value);
});

// 也是可以用 vue2 的 mounted, 但是抓變數會需要用 this 關鍵字, 造成混亂, 建議用 vue3 的 onMounted
// mounted() {
//     console.log(`The initial count is ${this.count}.`)
// }

// data() {
//   return {
//     count: 0
//   }
// },
// methods: {
//   increment() {
//     this.count++
//   }
// },
// mounted() {
//   console.log(`The initial count is ${this.count}.`)
// }
</script>

<template>
  <div>
    <h1>Vue {{ count }}</h1>
    <button @click="increment">Count is: {{ count }}</button>
    <HelloWorld></HelloWorld>
  </div>
</template>

<style></style>
