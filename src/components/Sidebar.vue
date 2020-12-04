<template>
  <div class="sidebar">
    <h1>Hello, I'm <br />Grace Evanggelisa</h1>

    <v-container class="px-0">
      <v-list-item v-for="menu in menus" :key="menu.title" class="pl-0">
        <v-btn :href="menu.link" color="#FFF3E0">
          <v-list-item-title
            v-text="menu.title"
            class="font brown--text text--darken-1"
          ></v-list-item-title>
        </v-btn>
      </v-list-item>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Sidebar",
  data: () => ({
    menus: [
      { title: "01 -- Profile", link: "#profile" },
      { title: "02 -- Projects", link: "#projects" },
      { title: "03 -- Contact", link: "#contact" },
    ],
  }),
};
</script>

<style scoped>
.menu {
  display: flex;
  flex-direction: column;
  margin-top: 20px;
}

.menu > * {
  margin-top: 30px;
  width: 200px;
  margin-left: 50%;
}

.sidebar {
  margin-top: 30vh;
  margin-left: 10vw;
}
</style>
