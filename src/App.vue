<template>
  <div id="app">
    <tabs :currentIndex="currentIndex" @changeIndex="getChangeIndex">
      <tab label="主页" index="1">
        <div>主页</div>
      </tab>
      <tab label="分类" index="2">
        <div>分类</div>
      </tab>
      <tab label="标签" index="3">
        <div>标签</div>
      </tab>
      <tab label="我的" index="4">
        <div>我的</div>
      </tab>
    </tabs>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      currentIndex: '1'
    }
  },
  methods: {
    getChangeIndex (index) {
      this.currentIndex = index
    }
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
}
#app {
  text-align: center;
  color: #2c3e50;
}
</style>
