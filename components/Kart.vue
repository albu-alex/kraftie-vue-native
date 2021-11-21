<template>
  <view :style="{flex: 1, backgroundColor: 'ghostwhite'}">
    <Header color="ghostwhite" />
    <text class="mainText">Produsele tale</text>
    <ProductLandscape :post-number="6" description="Amulete" class="productLandscape" />
    <ProductLandscape :post-number="7" description="Farfurie unica" class="productLandscape" />
    <text class="mainText">Total: 109 lei</text>
    <touchable-opacity :style="{borderRadius: 7, paddingHorizontal: 20}" class="payButton" :onPress="purchase">
      <text class="buttonText">Achită 109 lei</text>
    </touchable-opacity>
  </view>
</template>

<script>
import Header from "./Header";
import ProductLandscape from "./ProductLandscape";
export default {
  name: "Kart",
  components: {ProductLandscape, Header},
  props:{
    navigation:{
      type: Object
    }
  },
  methods:{
    purchase(){
      this.navigation.navigate('Profil')
    }
  }
}
</script>

<style>
.productLandscape{
  height: 150px;
  width: 90%;
  align-self: center;
  margin-top: 2%;
}
.mainText{
  color: #152679;
  align-self: center;
  font-weight: bold;
  font-size: 26px;
  margin-top: 4%;
  margin-bottom: 4%;
}
.buttonText{
  margin-top: 7px;
  color: #152679;
  align-self: center;
  justify-content: center;
  font-weight: 400;
  font-size: 20px;
}
.payButton{
  margin-top: 45%;
  background-color: #2CA6A4;
  align-self: center;
  align-items: center;
  align-content: center;
  height: 5%;
  width: 80%;
  border-width: 1px;
}
</style>