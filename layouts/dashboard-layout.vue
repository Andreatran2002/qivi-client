<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" :mini-variant.sync="mini" app>
      <v-list-item class="px-2">
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-title>John Leider</v-list-item-title>

        <v-btn icon @click.stop="mini = !mini">
          <v-icon>mdi-chevron-left</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list nav dense>
        <v-list-item :to="item.href" v-for="item in items" :key="item.title">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: true,
    items: [
      { title: "Home", icon: "mdi-home-city", href: "/dashboard/a" },
      { title: "My Account", icon: "mdi-account", href: "/dashboard/category" },
      { title: "Users", icon: "mdi-account-group-outline" },
    ],
    mini: true,
  }),
};
</script>
