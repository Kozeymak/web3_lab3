<template>
  <v-container fluid>
    <v-row dense>
      <v-col
          v-for="(item, i) in articles"
          :key="i"
          cols="4"
      >
        <v-card
            class="mx-auto"
            max-width="400"
            :link="true"
            :to="{name: 'detailedNews', params: {id: item.id}}"
        >
          <v-img
              class="white--text align-end"
              height="200px"
              :src="'/img/' + item.preview_image"
          >
            <v-card-title>{{ item.name }}</v-card-title>
          </v-img>

          <v-card-text class="text--primary">
            <div>{{ item.shortDesc }}</div>
          </v-card-text>

        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "News",

  computed: {
    articles() {
      return this.$store.getters.GET_ARTICLES;
    },
  },
};
</script>
