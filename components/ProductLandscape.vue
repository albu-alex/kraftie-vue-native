<template>
<view class="productLandscape">
  <view :style="{flexDirection: 'row', marginLeft: 10, marginTop: 5}">
    <FontAwesome5 name="user" :size="24" />
    <text class="userText">username</text>
  </view>
  <view :style="{flexDirection: 'row', marginLeft: 10, marginTop: 5}">
  <Image v-if="postNumber === 1" :source="require('../assets/globuri-1.jpg')"
         :style="{height: 100, width: 150, marginTop: 10, marginLeft: 10}" />
    <Image v-if="postNumber === 2" :source="require('../assets/globuri-2.jpg')"
           :style="{height: 100, width: 150, marginTop: 10, marginLeft: 10}" />
    <Image v-if="postNumber === 3" :source="require('../assets/globuri-3.jpg')"
           :style="{height: 100, width: 150, marginTop: 10, marginLeft: 10}" />
    <Image v-if="postNumber === 4" :source="require('../assets/globuri-4.jpg')"
           :style="{height: 100, width: 150, marginTop: 10, marginLeft: 10}" />
    <Image v-if="postNumber === 5" :source="require('../assets/globuri-5.jpg')"
           :style="{height: 100, width: 150, marginTop: 10, marginLeft: 10}" />
    <Image v-if="postNumber === 6" :source="require('../assets/photo1.jpg')"
           :style="{height: 100, width: 150, marginTop: 10, marginLeft: 10}" />
    <Image v-if="postNumber === 7" :source="require('../assets/photo2.jpg')"
           :style="{height: 100, width: 150, marginTop: 10, marginLeft: 10}" />
    <text class="mainText">{{description}}</text>
  </view>
</view>
</template>

<script>
import {FontAwesome5} from "@expo/vector-icons";
export default {
  name: "ProductLandscape",
  components:{
    FontAwesome5
  },
  props:{
    description: String,
    postNumber: Number,
  }
}
</script>

<style>
.productLandscape{
  border-color: #152679;
  border-width: 1px;
}
.userText{
  color: #152679;
  align-self: flex-start;
  font-weight: 400;
  font-size: 16px;
  margin-left: 3%;
}
.mainText{
  color: #152679;
  align-self: flex-start;
  font-weight: 600;
  font-size: 22px;
  margin-left: 3%;
  width: 50%;
}
</style>