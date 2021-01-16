<template>
<div>
   <v-chart
    :options = 'data'
  />
  echart  s
</div>
 
</template>

<script>
export default {
  data() {
    return {
      data: {
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
      }
    }
  }
}
</script>