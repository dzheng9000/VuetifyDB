<template>
  <v-card
    class="mx-auto"
    max-width="400"
    rounded
  >
    <v-list-item two-line>
      <v-list-item-content>
        <v-list-item-title class="headline">{{city}}</v-list-item-title>
        <v-list-item-subtitle>{{dayOfWeek}}, {{timeOfDay}}, {{forecast}}</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>

    <v-card-text>
      <v-row align="center">
        <v-col class="display-3" cols="6">
          {{temperature}}&deg;C
        </v-col>
        <v-col cols="6">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/sun.png"
            alt="Sunny image"
            width="92"
          ></v-img>
        </v-col>
      </v-row>
    </v-card-text>

    <v-list-item>
      <v-list-item-icon>
        <v-icon>mdi-send</v-icon>
      </v-list-item-icon>
      <v-list-item-subtitle>{{windSpeed}}</v-list-item-subtitle>
    </v-list-item>

    <v-list-item>
      <v-list-item-icon>
        <v-icon>mdi-cloud-download</v-icon>
      </v-list-item-icon>
      <v-list-item-subtitle>{{cloudiness}}</v-list-item-subtitle>
    </v-list-item>

    <v-list-item>
      <v-list-item-icon>
        <v-icon>mdi-compass</v-icon>
      </v-list-item-icon>
      <v-list-item-subtitle>{{windDirection}}</v-list-item-subtitle>
    </v-list-item>

    <v-divider></v-divider>


  </v-card>
</template>

<script>
  export default {
    name: 'Weather',
    props: {
      city: String,
      windSpeed: String,
      temperature: String,
      windDirection: String,
      dayOfWeek: String,
      timeOfDay: String,
      forecast: String,
      cloudiness: String
    }
  };
</script>

<style scoped>
  .weather {
    float: left;
  }
</style>