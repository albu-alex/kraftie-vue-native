<template>
<view class="product">
  <text v-if="photoSource === '1'" :style="{fontSize: 24}" class="mainText">Amulete</text>
  <text v-if="photoSource === '2'" :style="{fontSize: 24}" class="mainText">Farfurie unica</text>
  <text v-if="photoSource === '3'" :style="{fontSize: 24}" class="mainText">Farfurii handmade</text>
  <text v-if="photoSource === '4'" :style="{fontSize: 24}" class="mainText">Chitara handmade</text>
  <Image v-if="photoSource === '1'" :style="{width: 125, height: 250, alignSelf: 'center'}"
         :source="require(`../assets/photo1.jpg`)" />
  <Image v-if="photoSource === '2'" :style="{width: 125, height: 250, alignSelf: 'center'}"
         :source="require(`../assets/photo2.jpg`)" />
  <Image v-if="photoSource === '3'" :style="{width: 125, height: 250, alignSelf: 'center'}"
         :source="require(`../assets/photo3.jpg`)" />
  <Image v-if="photoSource === '4'" :style="{width: 125, height: 250, alignSelf: 'center'}"
         :source="require(`../assets/photo4.jpg`)" />
  <touchable-opacity :activeOpacity="0.6" :onPress="addToCart">
    <text class="addText">Adaugă în coș</text>
  </touchable-opacity>
</view>
</template>

<script>
export default {
  name: "Product",
  methods:{
    addToCart(){
      this.$emit('addToCart')
    }
  },
  props:{
    photoSource: String,
  }
}
</script>

<style>
.product{
  background-color: ghostwhite;
  border-width: 1px;
  width: 200px;
  height: 310px;
  border-color: dimgrey;
}
.mainText{
  color: #152679;
  align-self: center;
  font-weight: 500;
}.addText{
   color: #2CA6A4;
   align-self: center;
   font-weight: 500;
   margin-top: 5%;
 }
</style>