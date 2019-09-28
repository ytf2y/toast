<template>
  <div class="toast-page">
    <div class="body">
      <div class="title">{{title}}</div>
      <div class="content">
        <slot></slot>  <!-- 放置一个插槽(占位) -->
      </div>
      <div class="btns"> <span  @click="$emit('hidetoast')">取消</span><span class="confirm" @click="$emit('update:show',false)">确定</span> </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'toast',
  props: {
    btns: Array,
    show: Boolean,
    title: String  /* propTypes */
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .toast-page{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .toast-page .body{
    line-height: 40px;
    background-color: white;
    padding: 50px;
    border-radius: 10px;
  }
  .toast-page .body .title{
    text-align: center;
    font-weight: bold;
  }
  .toast-page .body .btns{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .toast-page .body .btns .confirm{
    color: red;
  }

</style>
