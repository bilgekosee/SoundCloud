<template>
  <v-navigation-drawer app color="#37584B" dark>
    <div class="text-center mt-5">
      <v-icon x-large>fa-brands fa-soundcloud fa-beat </v-icon>
      <v-btn class="mt-3" text color="" outlined> Get SoundCloud Pro </v-btn>
    </div>
    <h4 class="mt-6 ml-5 white--text">For You</h4>

    <v-list flat dense class="mt-5">
      <v-list-item-group v-model="selectedItem" color="#FFCA00">
        <v-list-item v-for="(item, i) in items" :key="i" active-class="border">
          <v-list-item-icon>
            <v-icon v-text="item.icon"></v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>

    <v-divider class="mx-10"></v-divider>

    <h4 class="mt-3 ml-5 white--text">Collection</h4>

    <v-list flat dense class="mt-5">
      <v-list-item-group>
        <v-list-item
          v-for="(item, i) in collections"
          :key="i"
          active-class="border"
        >
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
</template>

<script>
export default {
  data: () => ({
    selectedItem: 0,
    drawer: null,
    items: [
      { icon: "fa-light fa-bomb fa-xl", text: "Discover" },
      { icon: "fa-duotone fa-mug-hot fa-xl", text: "Stream" },
      { icon: "fas fa-user fa-xl", text: "Community" },
      { icon: "fas fa-chart-pie fa-xl", text: "Statistics" },
    ],
    collections: [
      { icon: "fas fa-heart", text: "Likes", route: "/likes" },
      { icon: "fas fa-music", text: "Playlists", route: "/playlists" },
      { icon: "fas fa-compact-disc", text: "Albums", route: "/albums" },
      { icon: "fas fa-podcast", text: "Podcasts", route: "/podcasts" },
      { icon: "fas fa-users", text: "Following", route: "/followings" },
    ],
  }),
};
</script>

<style scoped>
.border {
  border-right: 4px solid orangered;
}
</style>