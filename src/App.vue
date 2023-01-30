<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-app-bar-nav-icon app @click="drawer = !drawer" />
      <site-title :title="title" />
      <v-spacer />
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" location="left">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title"> Application </v-list-item-title>
          <v-list-item-subtitle> subtext </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-divider />
      <site-menu></site-menu>
    </v-navigation-drawer>

    <v-content>
      <router-view />
    </v-content>
    <site-footer :footer="footer"></site-footer>
  </v-app>
</template>

<script>
import SiteTitle from "@/components/SiteTitle.vue";
import SiteFooter from "@/components/SiteFooter.vue";
import SiteMenu from "@/components/SiteMenu.vue";

export default {
  components: { SiteTitle, SiteFooter, SiteMenu },
  name: "App",
  data() {
    return {
      drawer: false,
      title: "나의 타이틀입니다",
      footer: "푸터입니다",
    };
  },
};
</script>
