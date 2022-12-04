<template>
  <section class="container">
    <h2>{{ userName }}</h2>
  </section>
</template>

<script>
import { ref } from 'vue';

export default {
  // data() {
  //   return {
  //     userName: 'Alfredo',
  //   };
  // }
  setup() {
    const uName = ref('Alfredo');

    setTimeout(function () {
      uName.value = 'Fred';
    }, 2000);

    return {
      userName: uName
    };
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>