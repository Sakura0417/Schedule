<template>
    <div class="container">
        <el-container class="el-container">
            <el-aside width="200px" class="el-aside"><schedule-aside v-on:asidevalue="asidevalue"></schedule-aside>
            </el-aside>
            <el-container>
                <el-header class="el-header"><schedule-header></schedule-header></el-header>
                <el-main class="el-main"><schedule-main></schedule-main></el-main>
                <el-footer class="el-footer"><schedule-footer></schedule-footer></el-footer>
            </el-container>
        </el-container>
    </div>
</template>

<script>
import ScheduleAside from './components/aside'
import ScheduleHeader from './components/header'
import ScheduleMain from './components/main'
import ScheduleFooter from './components/footer'
export default {
  name: 'makeSchedule',
  components: {
    ScheduleAside,
    ScheduleHeader,
    ScheduleMain,
    ScheduleFooter
  },
  data () {
    return {
      value: ''
    }
  },
  methods: {
    asidevalue: function (schedulesetting) {
      this.value = schedulesetting
    }
  }
}
</script>

<style lang="stylus" scoped>
    .el-container

    .el-header .el-footer
        background-color #B3C0D1
        color #333
        text-align center
        line-height 60px

    .el-aside
        background-color #D3DCE6
        color #333
        text-align center
        line-height 200px

    .el-main
        background-color #E9EEF3
        color #333
        height 600px
        text-align center
        line-height 160px
</style>
