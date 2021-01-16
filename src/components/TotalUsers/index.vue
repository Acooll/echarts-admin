<template>
  <common-card title="累计用户数" value="1,087,503">
     <template>
      <div id='total-users-chart' :style="{width:'100%',height:'100%'}" />
    </template>
    <template v-slot:footer>
      <div class="total-users-footer">
        <span>日同比</span>
        <span class="emphasis">8.73%</span>
        <div class="increase" />
        <span class='month'>月同比</span>
        <span class="emphasis">35.91%</span>
      <div class="decrease" />
      </div>
    </template>
  </common-card> 
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'
export default {
  mixins: [commonCardMixin],
   mounted() {
    const chartDom = document.getElementById('total-users-chart')
    const chart = this.$echarts.init(chartDom)
    chart.setOption({
      grid:{
        left: 0,
        top: 0,
        right: 0,
        bottom: 0
      },
      xAxis:{
        type: 'value',
        show: false
      },
      yAxis:{
        type: 'category',
        show: false
      },
      series:[{
        type: 'bar',
        stack: '总量',
        data: [200],
        barWidth: 10,
        itemStyle: {
          color:'#45c946'
        }
      }, {
        type: 'bar',
        stack: '总量',
        data: [250],
         itemStyle: {
          color:'#eee'
        }
      }, {
        type: 'custom',
        stack:'总量',
        data: [200],
        renderItem: (params,api) => {
          const value = api.value(0)
          const endPoint = api.coord([value,0])

          return {
            type: 'group',
            position: endPoint,
            children: [{
              type: 'path',
              shape: {
              d: 'M128 320.001l383.744 383.744 383.744-383.744h-767.488z',
              x: -5,
              y: -20,
              width: 10,
              height: 8,
              layout: 'cover'
            },
            style: {
              fill: '#45c946'
            }
         },
         {
          type: 'path',
          shape: {
          d: 'M499.904 270.912l-342.912 395.584a16 16 0 0 0 12.032 26.496H855.04a16 16 0 0 0 12.032-26.496l-342.912-395.52a16 16 0 0 0-24.192 0z',
          x: -5,
          y: 10,
          width: 10,
          height: 8,
          layout: 'cover'
        },
        style: {
          fill: '#45c946'
        }
      }]
          }
        }    
      }
      ]
    })
  }
}
</script>

<style lang="stylus">
.total-users-footer
  display flex
  align-items center
  .month
    margin-left 10px
</style>
