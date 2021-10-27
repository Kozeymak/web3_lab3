<template>
  <v-container>
    <h1>Главная страница</h1>
    <v-carousel>
      <v-carousel-item
        v-for="(item, i) in articles"
        :key="i"
        :src="'/img/' + item.full_image"
        reverse-transition="fade-transition"
        transition="fade-transition"
      ></v-carousel-item>
    </v-carousel>
  </v-container>
</template>

<script>
export default {
  name: "Home",

  computed: {
    articles() {
      return this.$store.getters.GET_ARTICLES.filter(
        (item) => item.slider === true
      );
    },
  },

};
</script>
