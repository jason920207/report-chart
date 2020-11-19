<template>
  <common-card title="累计用户数" value="2,042,153">
    <template>
      <v-chart :options="getOptions()" />
    </template>
    <template v-slot:footer>
      <div class="total-user-footer">
        <span>日同比</span>
        <span class="emphsis"> 8.73%</span>
        <div class="increase"></div>
        <span class="month">月同比</span>
        <span class="emphsis"> 3.73%</span>
        <div class="decrease"></div>
      </div>
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
          type: 'value',
          show: false
        },
        yAxis: {
          type: 'category',
          show: false
        },
        series: [{
          type: 'bar',
          stack: '总量',
          data: [200],
          barWidth: 10,
          itemStyle: {
            color: '#45c946'
          }
        }, {
          type: 'bar',
          stack: '总量',
          data: [250],
          itemStyle: {
            color: '#eee'
          }
        }, {
          type: 'custom',
          data: [200],
          stack: '总量',
          renderItem: (params, api) => {
            const value = api.value(0)
            const endPoint = api.coord([value, 0])

            return {
              type: 'group',
              position: endPoint,
              children: [{
                type: 'path',
                shape: {
                  d: 'M128 355.84L154.432 320h716.416l25.152 34.56L535.872 704h-52.928L128 355.84z',
                  x: -5,
                  y: -20,
                  width: 10,
                  height: 10,
                  layout: 'cover'
                },
                style: {
                  fill: '#45C946'
                }
              }, {
                type: 'path',
                shape: {
                  d: 'M896 668.16l-26.432 35.84H153.152L128 669.44 488.128 320h52.928L896 668.16z',
                  x: -5,
                  y: 10,
                  width: 10,
                  height: 10,
                  layout: 'cover'
                },
                style: {
                  fill: '#45C946'
                }
              }]

            }
          }
        }
        ],
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
.total-user-footer {
  display: flex;
  flex-direction: row;
  align-items: center;
  .month {
    margin-left: 10px;
  }
}
</style>
