<template>
  <div class="pos">
      <el-row>
        <el-col :span="7" class="order-list">
          我是订单栏
        </el-col>
        <el-col :span="14">
          我是产品栏
        </el-col>
      </el-row>
  </div>
</template>

<script>
export default {
  name: "pos",
  mounted:function(){
    var orderListHeight = document.body.clientHeight
    console.log(orderListHeight)
    document.querySelector('.order-list').style.height = orderListHeight + 'px'
  },
}
</script>

<style scoped>
.order-list {
  background: #f2f2f2;
}
</style>
