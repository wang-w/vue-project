<template>
  <div class="search">
    <input class="serach-input" type="text" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" coped>
  @import "~styles/varibles.styl"
  .search
    height .72rem
    padding 0 .1rem
    background $bgColor
    .serach-input
      width 100%
      height .62rem
      padding 0 .1rem
      box-sizing border-box
      line-height .62rem
      text-align center
      border-radius .06rem
      color #666
      font-family "Microsoft Yahei"
</style>
