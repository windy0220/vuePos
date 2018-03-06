<template>
  <div class="pos">
      <el-row>
        <el-col :span="5" class="order-list">
          <el-tabs>
            <el-tab-pane label="点餐">
              <el-table :data="tableData" boder show-summary style="width:100%;">
                <el-table-column prop="goodsName"  width="100" label="商品"></el-table-column>
                <el-table-column prop="count" label="数量" width="50"></el-table-column>
                <el-table-column prop="price" label="价格" width="50"></el-table-column>
                <el-table-column  label="操作" width="100" fixed="right">
                  <template slot-scope="scope">
                    <el-button type="text" size="small">删除</el-button>
                    <el-button type="text" size="small">增加</el-button>
                  </template>
                </el-table-column>
              </el-table>
            </el-tab-pane>
            <el-tab-pane label="挂单">挂单</el-tab-pane>
            <el-tab-pane label="外卖">外卖</el-tab-pane>
          </el-tabs>

          <el-button type="warning">挂单</el-button>
          <el-button type="danger">删除</el-button>
          <el-button type="success">结账</el-button>
        </el-col>
        <el-col :span="17">
          <div class="title">常用商品</div>
          <div class="goods-list">
            <ul>
              <li v-for="goods in goodsList"><span>{{ goods.goodsName}}</span><span class="goods-price">￥{{ goods.price }}.00</span></li>
            </ul>
          </div>
          <div class="clear"></div>
          <div class="goods-type">
            <el-tabs>
              <el-tab-pane label="汉堡">
                <div class="type-goods-list">
                  <ul>
                    <li v-for="goods in type0Goods">
                      <img :src="goods.goodsImg" alt="">
                      <span class="type-goods-name">{{ goods.goodsName}}</span>
                      <span class="type-goods-price">￥{{ goods.price}}.00</span>
                    </li>
                  </ul>
                </div>
              </el-tab-pane>
              <el-tab-pane label="小食"></el-tab-pane>
              <el-tab-pane label="饮料"></el-tab-pane>
              <el-tab-pane label="套餐"></el-tab-pane>
            </el-tabs>
          </div>
        </el-col>
      </el-row>
  </div>
</template>

<script>
export default {
  name: "pos",
  mounted: function() {
    var orderListHeight = document.body.clientHeight;
    console.log(orderListHeight);
    document.querySelector(".order-list").style.height = orderListHeight + "px";
  },
  data() {
    return {
      tableData: [
        {
          goodsName: "可口可乐",
          price: 8,
          count: 1
        },
        {
          goodsName: "香辣鸡腿堡",
          price: 15,
          count: 1
        },
        {
          goodsName: "爱心薯条",
          price: 8,
          count: 1
        },
        {
          goodsName: "甜筒",
          price: 8,
          count: 1
        }
      ],
      goodsList: [
        {
          goodsId: 1,
          goodsName: "香辣鸡腿堡",
          price: 18
        },
        {
          goodsId: 2,
          goodsName: "田园鸡腿堡",
          price: 15
        },
        {
          goodsId: 3,
          goodsName: "和风汉堡",
          price: 15
        },
        {
          goodsId: 4,
          goodsName: "快乐全家桶",
          price: 80
        },
        {
          goodsId: 5,
          goodsName: "脆皮炸鸡腿",
          price: 10
        },
        {
          goodsId: 6,
          goodsName: "魔法鸡块",
          price: 20
        },
        {
          goodsId: 7,
          goodsName: "可乐大杯",
          price: 10
        },
        {
          goodsId: 8,
          goodsName: "雪顶咖啡",
          price: 18
        },
        {
          goodsId: 9,
          goodsName: "大块鸡米花",
          price: 15
        },
        {
          goodsId: 20,
          goodsName: "香脆鸡柳",
          price: 17
        }
      ],
      type0Goods:[
          {
              goodsId:1,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'香辣鸡腿堡',
              price:18
          }, {
              goodsId:2,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'田园鸡腿堡',
              price:15
          }, {
              goodsId:3,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'和风汉堡',
              price:15
          }, {
              goodsId:4,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'快乐全家桶',
              price:80
          }, {
              goodsId:5,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'脆皮炸鸡腿',
              price:10
          }, {
              goodsId:6,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'魔法鸡块',
              price:20
          }, {
              goodsId:7,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'可乐大杯',
              price:10
          }, {
              goodsId:8,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'雪顶咖啡',
              price:18
          }, {
              goodsId:9,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'大块鸡米花',
              price:15
          }, {
              goodsId:20,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'香脆鸡柳',
              price:17
          }
      ],
    }
  }
}
</script>

<style scoped>
.clear {
  clear: both;
}
.order-list {
  background: #f2f2f2;
}
.title {
  height: 40px;
  border-bottom: 1px solid #d3dce6;
  line-height: 40px;
  text-align: left;
  padding-left: 10px;
}
.goods-list {
  background: #f9fafc;
}
.goods-list ul li {
  list-style: none;
  display: block;
  float: left;
  background: #fff;
  border: 1px solid #ccc;
  padding: 5px;
  border-radius: 3px;
  margin: 5px;
}
.goods-list ul li:hover {
  background: #1d8ce0;
  color: #fff;
}
.goods-list ul li:hover .goods-price {
  color: #fff;
}
.goods-price {
  color: rgb(96, 135, 206);
}
.type-goods-list ul li{
  list-style: none;
  display: block;
  float: left;
  width: 200px;
  height: 50px;
  padding: 5px;
  margin: 5px;
  border: #ccc 1px solid;
  border-radius: 2px;
}
.type-goods-list ul li img{
  width: 50px;
  height: 50px;;
  float: left;
}
.type-goods-name{
  width: 130px;
  text-align: left;
  display: block;
  float: left;
  padding-left: 10px;
}
.type-goods-price{
  display: block;
  float: left;
  padding-left: 10px;
  margin-top: 10px;
  font-size: small;
  color: #1d8ce0;
}
</style>
