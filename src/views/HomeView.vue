<template>
  <v-app
    id="inspire"
    :style="{ background: $vuetify.theme.themes.dark.background }"
  >
    <SideBar />
    <v-container>
      <v-app-bar color="rgba(0,0,0,0)" flat class="mt-4">
        <v-row>
          <v-col cols="12" sm="3">
            <v-btn color="#FFCA00" outlined dark>
              <v-icon left>fas fa-upload</v-icon> Upload
            </v-btn>
          </v-col>
          <v-col cols="12" sm="6">
            <v-text-field
              label="Search..."
              filled
              append-icon="mdi-magnify"
              dense
              solo
              flat
              background-color="#695c55"
              dark
            >
            </v-text-field>
          </v-col>
          <v-col cols="12" sm="3">
            <div class="float-right mt-n1">
              <v-btn icon dark class="mr-n8"
                ><v-icon color="#37515F">fas fa-bell</v-icon></v-btn
              >
              <v-btn icon dark>
                <v-badge bordered overlap color="yellow" dot class="mr-n8">
                  <v-icon color="#37515F">fas fa-envelope</v-icon>
                </v-badge>
              </v-btn>
              <v-btn text color="#37515F">Bilge</v-btn>
              <v-avatar size="30" class="ml-n3">
                <v-img
                  src="https://pbs.twimg.com/profile_images/1672683083521306624/YrdSb_8v_400x400.jpg"
                ></v-img>
              </v-avatar>
              <v-btn icon dark class="ml-n3">
                <v-icon x-small color="#37515F">fas fa-chevron-down</v-icon>
              </v-btn>
            </div>
          </v-col>
        </v-row>
      </v-app-bar>
      <v-div class="d-flex flex-column justify-space-between align-center">
        <v-app-bar class="" color="#402225" flat>
          <v-icon color="#37515F">fas fa-caret-left</v-icon>
          <span class="ml-3 mr-3 white--text">My Heart Is Refusing Me</span>
          <v-icon color="#37515F">fas fa-caret-right</v-icon>
        </v-app-bar>
      </v-div>
      <carousel-3d :controls-visible="true" :clickable="false" :height="300">
        <slide :index="i" :key="i" v-for="(slide, i) in slides">
          <figure>
            <img :src="slide.src" />
            <figcaption>
              <v-btn text color="white">{{ slide.text }}</v-btn>
            </figcaption>
          </figure>
        </slide>
      </carousel-3d>
      <v-div class="d-flex flex-column justify-space-between align-center">
        <v-app-bar class="container2" color="#402225" flat>
          <v-btn text class="white--text">
            <v-icon left dark color="#9E2A2B">fas fa-caret-right</v-icon>3.6M
            Listeners
          </v-btn>
          <v-btn color="#FF9F00" dark>
            <v-icon left dark>fas fa-heart</v-icon>1.2M Likes
          </v-btn>
          <v-btn color="#19070F" dark class="ml-2">
            <v-icon left dark>fas fa-retweet</v-icon> 220k Reposts
          </v-btn>
          <v-btn color="#19070F" dark class="ml-2">
            <v-icon left dark>fas fa-share-square</v-icon> Share
          </v-btn>
          <v-btn color="#19070F" dark class="ml-2">
            <v-icon left dark>fas fa-share-square</v-icon> Share
          </v-btn>
          <v-btn color="#19070F" dark class="ml-2">
            <v-icon left dark>fas fa-ellipsis-h</v-icon> More
          </v-btn>
        </v-app-bar>
      </v-div>
      <v-div class="d-flex flex-column justify-space-between align-center">
        <v-row>
          <v-col cols="12" sm="2"></v-col>
          <v-col
            cols="12"
            sm="8"
            style="
              position: absolute;
              bottom: 0;
              margin-left: auto;
              margin-right: auto;
              left: 0;
              right: 0;
              text-align: center;
            "
          >
            <v-card tile color="#37584B" dark>
              <v-progress-linear
                :value="50"
                color="#FFCA00"
                class="my-0"
                height="3"
              ></v-progress-linear>
              <v-row>
                <v-col cols="12" sm="2">
                  <v-img
                    src="https://i.pinimg.com/564x/7f/4c/80/7f4c80f5746942cd54b8d8ee60de1df2.jpg"
                    max-height="40"
                    max-width="40"
                    class="mt-4 ml-2"
                  ></v-img>
                </v-col>
                <v-col cols="12" sm="1">
                  <h6 class="mt-5 ml-n16 grey--text text--ligten-4">
                    Sadness Will Last Forever<br />
                    <span class="grey--text text--darken-3">The Away Days</span>
                  </h6>
                </v-col>
                <v-col cols="12" sm="2">
                  <v-btn icon class="ml-n14 mt-4">
                    <v-icon>mdi-rewind</v-icon>
                  </v-btn>
                  <v-btn icon class="mt-4">
                    <v-icon color="#FFCA00">mdi-pause</v-icon>
                  </v-btn>
                  <v-btn icon class="mt-4">
                    <v-icon>mdi-fast-forward</v-icon>
                  </v-btn>
                </v-col>
                <v-col cols="12" sm="5">
                  <v-app-bar flat color="#37584B">
                    <span class="caption text-9xl ml-n14">01:36</span>
                    <v-slider
                      value="30"
                      color="#FFAD00"
                      class="mt-6"
                    ></v-slider>
                    <span class="caption text-9xl">04:13</span>
                  </v-app-bar>
                </v-col>
                <v-col cols="12" sm="1">
                  <v-btn icon class="mt-4">
                    <v-icon small>fas fa-undo</v-icon>
                  </v-btn>
                </v-col>
              </v-row>
            </v-card>
          </v-col>
        </v-row>
      </v-div>
    </v-container>
  </v-app>
</template>

<script>
import SideBar from "../components/SideBar.vue";
import { Carousel3d, Slide } from "vue-carousel-3d";
export default {
  data: () => ({
    slides: [
      { src: require("../../public/1.jpg"), text: "Looren" },
      { src: require("../../public/2.jpg"), text: "Imagene Dragons" },
      { src: require("../../public/3.jpg"), text: "Mehro" },
      { src: require("../../public/4.jpg"), text: "Tamino" },
      { src: require("../../public/5.jpg"), text: "Taylor Swift" },
      { src: require("../../public/6.jpg"), text: "Tom Odell" },
      { src: require("../../public/7.jpg"), text: "Low Roar" },
      { src: require("../../public/8.jpg"), text: "Adele" },
    ],
  }),

  components: {
    SideBar,
    Carousel3d,
    Slide,
  },
};
</script>

<style>
.carousel-3d-container figure {
  margin: 0;
}
.carousel-3d-container figcaption {
  position: absolute;
  background-color: rgba(0, 0, 0, 0.6);
  color: white;
  bottom: 0;
  position: absolute;
  padding: 15;
  font-size: 12;
  min-width: 100%;
  box-sizing: border-box;
}

.next span,
.prev span {
  color: #ffca00;
}
</style>
