<template>
  <common-card title="今日交易用户数" value="81,014">
    <template>
      <v-chart :options="getOptions()" />
    </template>
    <template v-slot:footer>
      <span>退货率</span>
      <span class="emphsis"> 5.14%</span>
    </template>
  </common-card>
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'
export default {
  mixins: [commonCardMixin],
  methods: {
    getOptions () {
      return {
        color: ['#3398DB'],
        series: [{
          type: 'bar',
          data: [410, 82, 200, 334, 390, 330, 220],
          barWidth: '60%'
        }],
        xAxis: {
          type: 'category',
          show: false,
          data: ['00:00', '01:00', '02:00', '03:00', '04:00', '05:00', '06:00']
        },
        yAxis: {
          show: false
        },
        grid: {
          top: 0,
          right: 0,
          bottom: 0,
          left: 0
        }
      }
    }
  }
}
</script>

<style lang="scss">
</style>
