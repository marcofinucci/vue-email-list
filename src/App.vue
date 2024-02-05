<script>
import axios from "axios";

export default {
  name: "App",
  data: () => ({
    emails: [],
  }),
  mounted() {
    for (let i = 0; i < 10; i++) {
      axios.get("https://flynn.boolean.careers/exercises/api/random/mail").then((response) => {
        this.emails.push(response.data.response);
      });
    }
  },
};
</script>

<template>
  <div v-for="email in emails" :key="email">
    <p>{{ email }}</p>
  </div>
</template>

<style scoped></style>
