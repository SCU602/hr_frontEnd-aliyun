<template>
  <div id="app">
    <!-- 路由占位符 -->
<!--    <router-view v-if="isReload"/>-->
    <router-view v-if="isReload"></router-view>
  </div>
</template>

<script>

export default {
  name: 'app',
  provide () {
    return {
      reload: this.reload
    }
  },
  data () {
    return {
      isRouterAlive: true,
      isReload: true
    }
  },
  methods: {
    reload() {
      this.isReload = false
      this.$nextTick(() => {
        this.isReload = true
      })
    }
    // reload () {
    //   this.isRouterAlive = false
    //   this.$nextTick(function () {
    //     this.isRouterAlive = true
    //   })
    // }
  }
}
</script>

<style>

</style>
