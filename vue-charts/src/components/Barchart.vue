<script>
    import { Bar } from 'vue-chartjs'

    export default {
    extends: Bar,
    mounted () {
        // Overwriting base render method with actual data.
        this.renderChart({
        labels: [ 'Social Security Tax', 'Medicare Tax', 'Income Tax', 'Capital Gains Tax',
         'Alternative Minimum Tax', 'Net Investment Income Tax'],
        datasets: [
            {
            label: 'Federal Taxes',
            backgroundColor: '#f87979',
            data: [1000, 12000, 181000, 0, 84000, 0]
            },
            {
            label: 'State Taxes',
            backgroundColor: '#dec9f1',
            data: [0, 0, 57000, 0, 7000, 0]
            }
        ]
        })
    }
    }
</script>
