<template>
  <common-card title="累计订单量" value="21,544,143">
     <template>
      <div id='total-orders-chart' :style="{width:'100%',height:'100%'}" />
    </template>
    <template v-slot:footer>
      <span>昨日订单量</span>
      <span class="emphasis">2,000,000</span>
    </template>
  </common-card> 
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'
export default {
  mixins: [commonCardMixin],
  mounted() {
    const chartDom = document.getElementById('total-orders-chart')
    console.log(this.$echarts)
    const chart =  this.$echarts.init(chartDom)
    chart.setOption({
      xAxis: {
        type: 'category',
        show: false,
        boundaryGap: false
      },
      yAxis: {
        show:false
      },
      series: [{
        type: 'line',
        data: [620,432,220,543,787,453,321,675,464,343,654,621,356,435],
        areaStyle:{
          color:'purple'
        },
        lineStyle:{
          width: 0
        },
        itemStyle: {
          opacity: 0
        },
        smooth: true
      }],
      grid: {
        top: 0,
        left: 0,
        bottom: 0,
        right: 0
      }
    })
  }
}
</script>

<style lang="stylus">

</style>