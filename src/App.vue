<template>
  <v-app>
    <Header />
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import Header from "./components/Header";

export default {
  components: { Header },

  created() {
    this.$store.dispatch("GET_ARTICLES");
  }
};
</script>

<style scoped></style>
