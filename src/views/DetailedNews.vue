<template>
  <v-container>
    <div class="text-h3 py-5 text-center">{{ article.name }}</div>
    <v-img
        :src="'/img/' + article.full_image"
        max-height="500"
        class="rounded-lg"
        alt=" "></v-img>
    <div class="text-body-1 py-3" >{{ article.desc }}</div>
    <div class="text-body-2 text-right font-weight-bold" >Опубликовано: {{ article.date }}</div>
  </v-container>
</template>

<script>
import axios from 'axios';

export default {
  name: "detailedNews",

  data() {
    return {
      article: null
    };
  },

  methods: {
    async getArticle() {
      try {
        let {data} = await axios.get('http://demo-api.vsdev.space/api/articles/' + this.$route.params.id);
        this.article = data;
      } catch (error) {
        console.log(error);
      }
    }
  },

  created() {
    this.getArticle();
  }
};
</script>

<style scoped>

</style>