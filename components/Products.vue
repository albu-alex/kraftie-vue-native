<template>
  <view :style="{marginBottom: 50}">
    <text class="mainText">{{title}}</text>
    <scroll-view :horizontal="true">
      <Product @addToCart="addToCart" photo-source="1" :style="{marginHorizontal: 10}" />
      <Product @addToCart="addToCart" photo-source="2" :style="{marginHorizontal: 10}" />
      <Product @addToCart="addToCart" photo-source="3" :style="{marginHorizontal: 10}" />
      <view :style="{flexDirection: 'row'}" v-for="product in products">
        <Product @addToCart="addToCart" photo-source="4" :style="{marginHorizontal: 10}" />
      </view>
    </scroll-view>
  </view>
</template>

<script>
import Product from "./Product";
export default {
  name: "Products",
  components: {
    Product
  },
  props: {
    products: Array,
    title: String
  },
  methods:{
    addToCart(){
      this.$emit("addToCart")
    }
  }
}
</script>

<style>
.mainText{
  color: #152679;
  align-self: flex-start;
  font-weight: bold;
  font-size: 26px;
  margin-left: 3%;
}
</style>