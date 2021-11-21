<template>
  <view class="header">
    <touchable-opacity class="logo1" :onpress="doNothing" :activeOpacity="0.6">
      <Ionicons name="ios-settings-outline" :size=24 color="ghostwhite" />
    </touchable-opacity>
    <text class="mainText">Kraftie</text>
    <touchable-opacity class="logo2" :onPress="doNothing" :activeOpacity="0.6">
    <FontAwesome5 name="shopping-basket" :size=24 :color="color" />
    </touchable-opacity>
  </view>
</template>

<script>
import { Ionicons, FontAwesome5 } from '@expo/vector-icons';
export default {
  name: "Header",
  components:{
    Ionicons,
    FontAwesome5
  },
  methods:{
    doNothing(){
      this.$emit("goToLogin")
    }
  },
  props:{
    color: String
  }
}
</script>

<style>
.header{
  background-color: #152679;
  flex-direction: row;
}
.logo1{
  margin-top: 11%;
  margin-left: 2%;
}
.logo2{
  margin-top: 11%;
  margin-left: 35%;
}
.mainText{
  font-size: 20px;
  font-weight: 600;
  color: ghostwhite;
  margin-top: 11%;
  margin-left: 32%;
}
</style>