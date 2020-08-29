<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-btn
        to='/'
        text
        depressed
      >
        <span class="mr-2">Dragon Boat Analytics</span>
        <v-icon>mdi-sail-boat</v-icon>
      </v-btn>
      <v-spacer></v-spacer>
      v0.0.1
    </v-app-bar>
   <v-main>
    <!-- Miss then and you're in for a headache -->
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
// import Weather from './components/Weather'

export default {
  name: "App",

  components: {
    // Weather
  },

  data: () => ({
    //
  })
};
</script>
