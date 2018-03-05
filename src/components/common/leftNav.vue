<template>
  <div class="left-nav">
    <ul>
      <li><i class="icon iconfont icon-zhangdan-xianxing"></i><span>收银</span></li>
      <li><i class="icon iconfont icon-dianpu-xianxing"></i><span>店铺</span></li>
      <li><i class="icon iconfont icon-shangpin-xianxing"></i><span>商品</span></li>
      <li><i class="icon iconfont icon-yonghu-xianxing"></i><span>会员</span></li>
      <li><i class="icon iconfont icon-zhexiantu-xianxing"></i><span>统计</span></li>
      <li><i class="icon iconfont icon-shezhi-xianxing"></i><span>设置</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "leftNav",
  data() {
    return {};
  }
};
</script>

<style scoped>
.left-nav {
  float: left;
  color: #fff;
  width: 100px;
  height: 100%;
  background: #1d8ce0;
  font-size: 24px;
}
ul, li{
  margin: 0;
  padding: 0;
}
li {
  text-align: center;
  list-style: none;
  display: block;
  width: 100px;
  height: 50px;
  line-height: 50px;
  border-bottom: 1px solid #20a0ff;
  cursor: pointer;
}
li:hover{
  background:#20a0fa;
}
li i{
margin-right: 5px;
font-size: 24px;
}
</style>
