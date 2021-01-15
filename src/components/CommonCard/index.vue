<template>
  <div class='common-card'>
    <div class='title'>{{title}}</div>
    <div class='value'>{{value}}</div>
    <div class='chart'>
      <slot></slot>
    </div>
    <div class='line' />
    <div class='total'>
      <slot name='footer'></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    value: String
  }
}

</script>

<style lang="stylus">
.title 
  font-size 12px
  color #999
.value
  font-size 20px
  color #000
  margin-top 5px
  letter-spacing 1px
  font-weight 500
.chart 
  height 50px
.line
  margin 10px 0
  border-top 1px solid #eee
.total
  color #666
  font-size 20px      
</style>