<template>
  <v-app>
    <v-app-bar app color="success" dark elevation="1" >
      <v-app-bar-nav-icon @click.stop="sidebar = !sidebar"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-icon> mdi-account</v-icon>
    </v-app-bar>
    <v-navigation-drawer app v-model="sidebar" :mini-variant.sync="mini">
      <v-list dense color="success" dark>
        <v-list-item>
          <v-list-item-action>
            <v-icon class="px=2" @click.stop="sidebar = !sidebar">mdi-chevron-left</v-icon>
          </v-list-item-action>
          <v-list-item-title>
          <h3>Minha Lista de Tarefas</h3>
        </v-list-item-title>
        </v-list-item>
      </v-list>
      <v-list-item @click="mini = !mini">
        <v-list-item-avatar>
          <v-icon>mdi-account</v-icon>
        </v-list-item-avatar>
        <v-list-item-content>Gabriel da Maia Leandro</v-list-item-content>
        <v-btn icon smal><v-icon>mdi-chevron-left</v-icon></v-btn>
      </v-list-item>
      <v-divider></v-divider>
        <v-list>
          <v-list-item v-for="item of items" v-bind:key="item.title" link :to="item.to">
            <v-list-icon>
              <v-icon>{{item.icon}}</v-icon>
            </v-list-icon> 
            <v-list-item-content>{{item.title}}</v-list-item-content>
          </v-list-item>
        </v-list>
    </v-navigation-drawer>
    <v-main><router-view>
      </router-view></v-main>
    <v-footer app class="py-3">
      <span class="caption">MyTodoList &copy;2021</span></v-footer>

  </v-app>
</template>

<script>
export default {
  data() {
    return {
      sidebar: true,
      mini: false,
      items: [
        { title: "Home", icon:"mdi-account", to:"/"},
        { title: "Perfil", icon:"mdi-account-cog", to:"/perfil"},
        { title: "Sair", icon:"mdi-exit-to-app", to:"/login"},
      ],
    };
  }
}
</script>

<style>

</style>