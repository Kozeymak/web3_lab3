<template>
  <div>
    <div v-if="comments" class="text-h4 pt-13">Комментарии:</div>
    <v-card
      v-for="(item, i) in comments"
      :key="i"
      class="mx-auto mt-4"
      max-width="100%"
    >
      <v-card-title>{{ item.user_name }}:</v-card-title>

      <v-card-text class="text-body-1">
        {{ item.comment }}
      </v-card-text>
    </v-card>
    <Form v-if="comments"/>
  </div>
</template>

<script>
import axios from "axios";
import Form from "./addCommentForm/Form";

export default {
  name: "Comments",
  components: { Form },
  data() {
    return {
      comments: null,
    };
  },

  methods: {
    async getComments() {
      let { data } = await axios.get(
        `http://demo-api.vsdev.space/api/articles/${this.$route.params.id}/comments`
      );
      this.comments = data.reverse();
    },
  },

  created() {
    this.getComments();
  },
};
</script>

<style scoped></style>
