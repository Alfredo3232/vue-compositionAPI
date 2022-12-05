<template>
  <section class="container">
    <h2>{{ uName }}</h2>
    <h3>{{ uAge }}</h3>

    <button @click="setNewAge">Change Age</button>

    <div>
      <input type="text" placeholder="First Name" @input="setFirstName" />
      <input type="text" placeholder="Last Name" @input="setLastName" />
    </div>
  </section>
</template>

<script>
import { ref, computed } from 'vue';

export default {
  setup() {
    // Data
    let firstName = ref('');
    let lastName = ref('');
    let uAge = ref(21);

    // Computed
    let uName = computed(() => {
      return firstName.value + ' ' + lastName.value;
    });

    // Methods
    function setNewAge() {
      uAge.value = 22;
    }

    function setFirstName(event) {
      firstName.value = event.target.value;
    }

    function setLastName(event) {
      lastName.value = event.target.value;
    }

    // Return
    return {
      uName,
      uAge,
      setNewAge,
      setFirstName,
      setLastName
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