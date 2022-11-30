<script>
import { onMounted, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";

export default {
  components: {
    HelloWorld,
  },
  props: {
    data: {
      type: Object,
      default: () => ({}),
    },
  },
  setup() {
    const count = ref(0);
    const increment = () => {
      count.value += 1;
    };

    onMounted(() => {
      console.log(count.value);
    });

    return { count, increment };
  },
  // 也是可以用 vue2 的 mounted, 但是抓變數會需要用 this 關鍵字, 造成混亂, 建議用 vue3 的 onMounted
  // mounted() {
  //     console.log(`The initial count is ${this.count}.`)
  // }

  // // Vue2 寫法
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
};
</script>

<template>
  <div>
    <h1>Vue {{ count }}</h1>
    <button @click="increment">Count is: {{ count }}</button>
    <HelloWorld></HelloWorld>
  </div>
</template>

<style></style>
