<template>
    <div class="aside_container">
        <el-row >
            <el-col :span="24">
                <el-menu
                        default-active="1"
                        class="el-menu-vertical-demo">
                    <el-menu-item  index="1" @click='click_schedule'>
                        <i class="el-icon-menu"></i>
                        <span slot="title">值班表</span>
                    </el-menu-item>
                    <el-menu-item  index="2" @click='click_setting'>
                        <i class="el-icon-setting"></i>
                        <span slot="title">设置</span>
                    </el-menu-item>
                </el-menu>
            </el-col>
        </el-row>
    </div>
</template>

<script>
export default {
  name: 'ScheduleAside',
  data () {
    return {
      schedulesetting: 'select_schedule'
      // childValue: '我是子组件的数据'
    }
  },
  methods: {
    click_schedule: function () {
      this.schedulesetting = 'select_schedule'
      this.$emit('asidevalue', this.schedulesetting)
      // this.$emit('childByValue', this.childValue)
    },
    click_setting: function () {
      this.schedulesetting = 'select_setting'
      this.$emit('asidevalue', this.schedulesetting)
    }
  }
}
</script>

<style lang="stylus" scoped>
    .aside_container
        margin-top 80px
</style>
