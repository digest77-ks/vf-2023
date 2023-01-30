<template>
  <v-list v-model:opened="open">
    <v-list-group value="home">
      <template v-slot:activator="{ props }">
        <v-list-item v-bind="props" title="home" prepend-icon="mdi-home">
        </v-list-item>
      </template>

      <v-list-item
        v-for="([title, to], i) in home"
        :key="i"
        :title="title"
        :to="to"
        :value="title"
      ></v-list-item>
    </v-list-group>

    <v-list-group value="about">
      <template v-slot:activator="{ props }">
        <v-list-item
          v-bind="props"
          prepend-icon="mdi-account-circle"
          title="about"
        ></v-list-item>
      </template>

      <v-list-item
        v-for="([title, to], i) in about"
        :key="i"
        :title="title"
        :to="to"
        :value="title"
      ></v-list-item>
    </v-list-group>
  </v-list>
</template>

<script>
export default {
  // props: ["footer"],
  data() {
    return {
      open: ["home", "about"],
      home: [
        ["Dashboard", "/"],
        ["About", "/about"],
      ],
      about: [["About", "/about"]],

      // items: [
      //   {
      //     title: "home",
      //     subItems: [
      //       {
      //         title: "Dashboard",
      //         to: "/",
      //       },
      //       {
      //         title: "About",
      //         to: "/about",
      //       },
      //     ],
      //   },
      //   {
      //     title: "about",
      //     active: true,
      //     // icon: 'mdi-account',
      //     subItems: [
      //       {
      //         title: "about",
      //         to: "/about",
      //       },
      //     ],
      //   },
      // ],
    };
  },
};
</script>
