<template>
  <v-data-table
    :headers="headers"
    :items="lanes"
    :items-per-page="6"
    class="elevation-1"
    dense
  ></v-data-table>
</template>


<script>
  export default {
  	name: "RaceTable",
    data () {
      return {
        headers: [
          {
            text: 'Lane',
            align: 'start',
            sortable: false,
            value: 'laneNumber',
          },
          { text: 'Team', value: 'boat' },
          { text: 'Finish', value: 'finish' },
          { text: 'Time', value: 'time' }
        ],
        lanes: [
          {
            laneNumber: '1',
            boat: "Alameda DragonFlyers",
            finish: 4,
            time: "02:22.49"
          },
          {
            laneNumber: '2',
            boat: "Dieselfish Youth",
            finish: 5,
            time: "02:22.72"
          },
          {
            laneNumber: '3',
            boat: "Ripple Effect Fast",
            finish: 1,
            time: "02:12.64",
          },
          {
            laneNumber: '4',
            boat: "Bay Area Dragons by LinkedIn",
            finish: 2,
            time: "02.12.46"
          },
          {
            laneNumber: '5',
            boat: "SF Dragon Healers Gold",
            finish: 3,
            time: "02:17.68"
          },
          {
            laneNumber: '6',
            boat: "Open",
            finish: 6,
            time: "09.00.00"
          }
        ],
      }
    },
  }
</script>