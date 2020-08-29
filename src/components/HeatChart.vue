<script>
  import { Bar } from 'vue-chartjs'
  export default {
    name: "HeatChart",
    props: {
      finishTimes: Array,
      finishTimesStrings: Object
    },
    extends: Bar,
    data () {
      return {
        datacollection: {
          //Data to be represented on x-axis
          labels: ['Lane1', 'Lane2', 'Lane3', 'Lane4', 'Lane5', 'Lane6'],
          datasets: [
            {
              label: 'Heat R4',
              backgroundColor: '#f87979',
              pointBackgroundColor: 'white',
              borderWidth: 1,
              pointBorderColor: '#249EBF',
              //Data to be represented on y-axis
              data: this.finishTimes,
              barThickness: 'flex',
              finishTimes: this.finishTimesStrings
            }
          ]
        },
        //Chart.js options that controls the appearance of the chart
        options: {
          tooltips: {
            callbacks: {
                label: function(tooltipItem, data) {
                      console.log(data);
                      console.log(data.datasets[tooltipItem.datasetIndex]['finishTimes'][tooltipItem.xLabel])
                      return(data.datasets[tooltipItem.datasetIndex]['finishTimes'][tooltipItem.xLabel]);
                }
            }
          },
          layout: {
            
          },
          scales: {
            yAxes: [{
              ticks: {
                display: false
              },
              gridLines: {
                drawBorder: false
              }
            }],
            xAxes: [ {
              gridLines: {
                display: false
              }
            }]
          },
          responsive: false,
          maintainAspectRatio: false
        }
      }
    },
    mounted () {
      //renderChart function renders the chart with the datacollection and options object.
      this.renderChart(this.datacollection, this.options)
    }
  }
</script>
