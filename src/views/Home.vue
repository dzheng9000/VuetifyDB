<template>
<div>
  
  <v-img src=../assets/lake_merritt_2018.png height=280 class="raceMap" width=300 dark></v-img>
  <RaceTable/>
  <HeatChart v-bind:finishTimes="convertToMillisecondsList(['02:22.49', '02:22.72', '02:12.64', '02.12.46', '02:17.68', '00.00.00'])"
  			 v-bind:finishTimesStrings="{
  			 	Lane1:'02:22.49',
  			 	Lane2:'02:22.72', 
  			 	Lane3:'02:12.64', 
  			 	Lane4:'02.12.46', 
  			 	Lane5:'02:17.68', 
  			 	Lane6:'00.00.00'}"/>
  <div>
    <Weather city="Oakland" windSpeed="24 mi/h" temperature="58" windDirection="W"
    dayOfWeek="Monday" timeOfDay="08:30 AM" forecast="Sunny" cloudiness="Partly Cloudy"/>
  </div>
</div>
</template>

<script>
// @ is an alias to /src
import Weather from '../components/Weather'
import RaceTable from '../components/RaceTable'
import HeatChart from '../components/HeatChart'

export default {
  name: "Home",
  data() {
  	return {
  		weatherData: [{'city': 'San Francisco', 'windSpeed': '50 km/h', 'temperature': '78', 'windDirection': 'NW', 'dayOfWeek': 'Monday', 'timeOfDay': '12:00 AM', 'forecast': 'Sunny', 'cloudiness': '23%'}]
  	}
  },
  methods: {
  	convertToMilliseconds(timeStr) {
  		let milli = 0;
  		milli += parseInt(timeStr.substring(0, 2)) * 60000;
  		milli += parseInt(timeStr.substring(3, 5)) * 1000;
  		milli += parseInt(timeStr.substring(6, 8)) * 10;
  		return milli;
  	},
  	convertToMillisecondsList(timeStrList) {
  		let finishTimesList = [];
  		for (let i = 0; i < timeStrList.length; i++) {
  			finishTimesList.push(this.convertToMilliseconds(timeStrList[i]));
  		}
  		return finishTimesList;
  	}
  },
  components: {
  	Weather,
  	RaceTable,
  	HeatChart
  }
};

</script>

<style scoped>
	.raceMap {
		float: right;
	}
</style> 