<template>
  <div id="app">
    <button @click="showFlag=true">点击显示toast组件</button>
    <!-- <Toast v-show="showFlag"  title="自定义的title" :show="showFlag" @update:show=""> -->
    <Toast v-show="showFlag" :btns="['取消','确定']" title="自定义的title" :show.sync="showFlag" >
      <div style="color:red;">我是自定义的组件内容</div>
      <div style="color:red;">我是自定义的组件内容</div>
    </Toast>
  </div>
</template>

<script>
import Toast from './components/Toast.vue'

export default {
  name: 'app',
  data:function()
  {
    return {
      showFlag:false//控制toast组件的显示隐藏
    }
  },
  components: {
    Toast
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
