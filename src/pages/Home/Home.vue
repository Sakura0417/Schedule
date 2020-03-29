<template>
    <div class="container">
        <home-header></home-header>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
export default {
  name: 'Home',
  components: {
    HomeHeader
  }
}
</script>

<style lang="stylus" scoped>
    .container
        /*display bolck*/
        ///*text-align center*/
        width 100%
        height 600px
        padding-top   50px
        /*background-color aqua*/
</style>
