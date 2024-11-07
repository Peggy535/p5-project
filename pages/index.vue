<script setup>
import { ref, onMounted } from "vue";

const p5Container = ref(null);
const { $p5 } = useNuxtApp();
onMounted(() => {
  new $p5((p) => {
    p.setup = () => {
      p.createCanvas(p.windowWidth, p.windowHeight);
    };
    p.draw = () => {
      p.background("navy"); //navy background
    };
  }, p5Container.value);
});
</script>
<template>
  <div>
    <main class="w-screen min-h-dvh overflow-x-hidden relative" role="main">
      <div
        ref="p5Container"
        class="absolute top-0 left-0 w-full h-full z-10"
      ></div>
    </main>
  </div>
</template>
