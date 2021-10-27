<template>
  <h1>{{ article }}</h1>
</template>

<script>
import axios from 'axios'

export default {
  name: "detailedNews",

  data() {
    return {
      article: null
    }
  },

  methods: {
    async getArticle () {
      try {
        let {data} = await axios.get('http://demo-api.vsdev.space/api/articles/' + this.$route.params.id)
        this.article = data
      } catch (error) {
        console.log(error)
      }
    }
  },

  created() {
    this.getArticle()
  }
};
</script>

<style scoped>

</style>