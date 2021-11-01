<template>
  <v-container>
    <div class="text-h3 py-5 text-center">{{ article.name }}</div>
    <v-img
      :src="'/img/' + article.full_image"
      max-height="500"
      class="rounded-lg"
      alt=" "
    ></v-img>
    <div class="text-body-1 py-3">{{ article.desc }}</div>
    <div class="text-body-2 text-right font-weight-bold">
      Опубликовано: {{ article.date }}
    </div>
    <Comments />
  </v-container>
</template>

<script>
// import axios from "axios";
import Comments from "../components/Comments";

export default {
  name: "detailedNews",
  components: { Comments },

  // data() {
  //   return {
  //     article: null,
  //   };
  // },

  computed: {
    article() {
      return this.$store.getters.GET_ARTICLES[this.$route.params.id - 1];
    },
  },

  // methods: {
  //   async getArticle() {
  //     try {
  //       let { data } = await axios.get(
  //         "http://demo-api.vsdev.space/api/articles/" + this.$route.params.id
  //       );
  //       this.article = data;
  //     } catch (error) {
  //       console.log(error);
  //     }
  //   },
  // },

  // created() {
  //   this.getArticle();
  // },
};
</script>

<style scoped></style>
