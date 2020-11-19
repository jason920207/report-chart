<template>
  <common-card title="累计订单量" value="2,042,153">
    <template>
      <v-chart :options="getOptions()" />
    </template>
    <template v-slot:footer>
      <span>昨日订单量</span>
      <span class="emphsis"> 2,000,000</span>
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
        xAxis: {
          type: 'category',
          show: false,
          boundaryGap: false
        },
        yAxis: {
          show: false
        },
        series: [{
          type: 'line',
          data: [620, 432, 220, 532, 321, 432, 123, 432],
          areaStyle: {
            color: 'purple'
          },
          lineStyle: {
            width: 0
          },
          itemStyle: {
            opacity: 0
          },
          smooth: true
        }],
        grid: {
          top: 0,
          bottom: 0,
          left: 0,
          right: 0
        }
      }
    }
  }
}

</script>

<style lang="scss">
</style>
