<template>
  <div>
    <h1>{{ cont }}</h1>
    <h3>{{ welcome }}</h3>
    <button v-on:click="updateWelcome">click</button>
  </div>
</template>

<script>
export default {
  props: ["cont"],
  data() {
    return {
      isT: false,
      welcome: "",
    };
  },
  methods: {
    updateWelcome() {
      this.welcome = "최성진님 환영합니다!";
    },
  },
};
</script>

<style></style>
