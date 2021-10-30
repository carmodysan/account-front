<template>
  <!--<div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>-->
  <v-app v-cloak>
        <v-navigation-drawer permanent clipped app>
            <v-list dense nav>
                <v-list-item-group v-model="selectedItem" color="primary">
                    <v-list-item
                        v-for="(item, i) in items"
                        :key="i"
                        :to="item.to">
                        <v-list-item-icon>
                            <v-icon v-text="item.icon"></v-icon>
                        </v-list-item-icon>

                        <v-list-item-content>
                            <v-list-item-title v-text="item.text"></v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>
        <v-app-bar short clipped-left app>
            <v-app-bar-nav-icon></v-app-bar-nav-icon>
            <v-toolbar-title>Mon site perso</v-toolbar-title>
        </v-app-bar>
        <v-main>
            <v-container fluid>
                <router-view></router-view>
            </v-container>
        </v-main>
    </v-app>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

<script>
export default {
    name: "App",
    data: () => ({
        selectedItem: 0,
        items: [
            { text: 'Home', icon: 'mdi-folder', to: '/home' },
            { text: 'Month Account', icon: 'mdi-history', to: '/months' },
            { text: 'About', icon: 'mdi-upload', to: '/about' },
            { text: 'Shared with me', icon: 'mdi-account-multiple' },
            { text: 'Offline', icon: 'mdi-check-circle' },
            { text: 'Backups', icon: 'mdi-cloud-upload' },
            { text: 'Starred', icon: 'mdi-star' },
        ],
    }),
};
</script>

