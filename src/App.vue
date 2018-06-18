<template>
  <div id="app">
    <!--显示当前路由组件-->
    <router-view></router-view>
    <FooterGuide v-show="$route.meta.showFooter"/>
  </div>
</template>

<script>
  import FooterGuide from './components/FooterGuide/FooterGuide.vue'

  export default {
    components: {
      FooterGuide
    },
    mounted () {
      // 通知action获取地址信息
      this.$store.dispatch('getAddress')
      // 通知action获取用户信息
      this.$store.dispatch('getUserInfo')
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #app
    width 100%
    height 100%
    position relative
</style>
