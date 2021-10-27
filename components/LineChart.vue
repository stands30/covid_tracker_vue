<script>
import { Line } from 'vue-chartjs';
import moment from 'moment';
export default {
  extends: Line,
  methods: {
      initChart:function(countryReport){
          const vim = this;
                this.renderChart({
                    labels: countryReport.map(({ Date })=>  moment(String(Date)).format('DD/MM/YYYY')),
                    datasets:[{
                        data:countryReport.map( ({ Confirmed })=> Confirmed),
                        label: 'Infected',
                        borderColor: 'rgb(39, 173, 237)',
                        fill:true,
                    },{
                        data:countryReport.map( ({ Deaths })=> Deaths),
                        label: 'Deaths',
                        borderColor: 'red',
                        backgroundColor: 'rgba(255,0,0,0.5)',
                        fill:true,
                    },{
                        data:countryReport.map( ({ Recovered })=> Recovered),
                        label: 'Recovered',
                        borderColor: 'green',
                        backgroundColor: 'rgb(0 255 165 / 50%)',
                        fill:true,
                    }]
                }, {responsive: true});
      }
  },    
}
</script>