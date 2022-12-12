<template>
  <section class="container">
    <user-data :first-name="firstName" :last-name="lastName" :age="uAge"></user-data>

    <button @click="setNewAge">Change Age</button>

    <div>
      <input type="text" placeholder="First Name" v-model="firstName" />
      <input type="text" placeholder="Last Name" ref="lastNameInput" />
      <button @click="setLastName">Set Last Name</button>
    </div>
  </section>
</template>

<script>
import { ref, computed, watch } from "vue";
import UserData from "./components/UserData.vue";

export default {
  components: {
    'user-data': UserData
  },
  setup() {
    // Data
    let firstName = ref("");
    let lastName = ref("");
    let lastNameInput = ref(null);
    let uAge = ref(21);

    // Computed
    let uName = computed(() => {
      return firstName.value + " " + lastName.value;
    });

    // Watch
    watch([uAge, uName], function (newVals, oldVals) {
      console.log("Old age: " + oldVals[0]);
      console.log("New age: " + newVals[0]);

      console.log("Old name: " + oldVals[1]);
      console.log("New name: " + newVals[1]);
    });

    // Methods
    function setNewAge() {
      uAge.value = 22;
    }

    function setLastName() {
      lastName.value = lastNameInput.value.value;
    }

    // Return
    return {
      uName,
      uAge,
      setNewAge,
      firstName,
      lastName,
      lastNameInput,
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