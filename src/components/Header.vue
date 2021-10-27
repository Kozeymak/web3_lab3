<template>
  <div>
    <v-app-bar color="blue-grey darken-2" dark app>
      
      <div class="logo" @click="$router.push('/')">
        <v-icon size="30">mdi-newspaper</v-icon>
        <v-toolbar-title class="text-h5" style="margin-left: 10px"
        >ПолиНовости
        </v-toolbar-title>
      </div>
      
      <v-spacer></v-spacer>
      <v-text-field class="shrink" hide-details="auto"></v-text-field>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary right>
      <v-list nav>
        <v-list-item-group
            v-model="group"
            active-class="blue-grey--text"
        >
            <v-list-item @click="$router.push('/')">
              <v-list-item-icon>
                <v-icon>mdi-home</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Главная</v-list-item-title>
            </v-list-item>

            <v-list-item @click="$router.push('/news')">
              <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Новости</v-list-item-title>
            </v-list-item>

          <v-list-item @click="$router.push('/gallery')">
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Галерея</v-list-item-title>
          </v-list-item>
          
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "Header",
  data: () => ({
    drawer: false,
    group: null,
  }),
};
</script>

<style scoped>
.logo {
  display: flex;
  cursor: pointer;
  opacity: .8;
  transition: all .3s;
}

.logo:hover {
  opacity: 1;
}
</style>
