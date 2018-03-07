<template>
  <div class="pos">
      <el-row>
        <el-col :span="7" class="order-list">
          <el-tabs>
            <el-tab-pane label="点餐">
              <el-table :data="tableData" boder style="width:100%;">
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
              <el-tab-pane label="小食">
                <div class="type-goods-list">
                  <ul>
                    <li v-for="goods in type1Goods">
                      <img :src="goods.goodsImg" alt="">
                      <span class="type-goods-name">{{ goods.goodsName}}</span>
                      <span class="type-goods-price">￥{{ goods.price}}.00</span>
                    </li>
                  </ul>
                </div>
              </el-tab-pane>
              <el-tab-pane label="饮料">
                <div class="type-goods-list">
                  <ul>
                    <li v-for="goods in type2Goods">
                      <img :src="goods.goodsImg" alt="">
                      <span class="type-goods-name">{{ goods.goodsName}}</span>
                      <span class="type-goods-price">￥{{ goods.price}}.00</span>
                    </li>
                  </ul>
                </div>
              </el-tab-pane>
              <el-tab-pane label="套餐">
                <div class="type-goods-list">
                  <ul>
                    <li v-for="goods in type3Goods">
                      <img :src="goods.goodsImg" alt="">
                      <span class="type-goods-name">{{ goods.goodsName}}</span>
                      <span class="type-goods-price">￥{{ goods.price}}.00</span>
                    </li>
                  </ul>
                </div>
              </el-tab-pane>
            </el-tabs>
          </div>
        </el-col>
      </el-row>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "pos",
  created: function() {
    axios
      .get("http://jspang.com/DemoApi/oftenGoods.php")
      .then(Response => {
        console.log(Response);
        this.goodsList = Response.data;
      })
      .catch(Error => {
        console.log(Error);
      });

    axios
      .get("http://jspang.com/DemoApi/typeGoods.php")
      .then(Response => {
        console.log(Response);
        this.type0Goods = Response.data[0];
        this.type1Goods = Response.data[1];
        this.type2Goods = Response.data[2];
        this.type3Goods = Response.data[3];
      })
      .catch(Error => {
        console.log(Error);
      });
  },
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
      goodsList: [],
      type0Goods: [],
      type1Goods: [],
      type2Goods: [],
      type3Goods: [],
    };
  }
};
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
.type-goods-list ul li {
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
.type-goods-list ul li img {
  width: 50px;
  height: 50px;
  float: left;
}
.type-goods-name {
  width: 130px;
  text-align: left;
  display: block;
  float: left;
  padding-left: 10px;
}
.type-goods-price {
  display: block;
  float: left;
  padding-left: 10px;
  margin-top: 10px;
  font-size: small;
  color: #1d8ce0;
}
</style>
