<template>
  <div>
    <h1>Welcome My HomePage</h1>
    <h2>{{ name }}</h2>
    <Jin cont="메인페이지 내용입니다"></Jin>
  </div>
</template>

<script>
// @ is an alias to /src
import Jin from "@/components/Jin.vue";
export default {
  data() {
    return {
      name: "최성진",
    };
  },
  components: {
    Jin: Jin,
  },
};
</script>

<style>
h1 {
  color: aquamarine;
}
</style>
