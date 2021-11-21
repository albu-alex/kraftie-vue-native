<template>
  <view :style="{backgroundColor: 'ghostwhite', flex: 1}">
     <Header @goToLogin="goToLogin" :color="color" />
    <touchable-opacity :style="{height: 100}" :onPress="goToSearch" :activeOpacity="0.5">
       <Ionicons :style="{paddingLeft: 22, zIndex: 2, paddingTop: 30}" name="ios-search-outline" :size=24 color="#152679" />
       <text-input :autoCorrect="false" placeholderTextColor="#152679" :style="{paddingVertical: 5, borderRadius: 10, paddingHorizontal: 25, marginTop: -32}"
                  placeholder="Caută ceea ce dorești" class="textInputDark"
                  keyboardAppearance="dark" />
    </touchable-opacity>
      <scroll-view :automaticallyAdjustContentInsets="true" :directionalLockEnabled="true">
        <Products title="Populare" @addToCart="addToCart" :products="products" />
        <Products title="Oferte" @addToCart="addToCart" :products="products" />
      </scroll-view>
  </view>
</template>

<script>
import Header from "./Header";
import Products from "./Products";
import {Ionicons} from "@expo/vector-icons"
export default {
  beforeMount(){
    this.products.push({'key': 1})
    this.products.push({'key': 2})
    this.products.push({'key': 3})
    this.products.push({'key': 4})
  },
  data(){
    return{
      products: [],
      color: 'ghostwhite'
    }
  },
  name: "HomePage",
  components:{
    Products,
    Header,
    Ionicons
  },
  props:{
    navigation:{
      type: Object
    }
  },
  methods:{
    goToSearch(){
      this.navigation.navigate('Caută')
    },
    addToCart(){
      alert("Produs adaugat cu succes!")
      this.color = '#E3170A'
    },
    goToLogin(){
      this.navigation.navigate('Kart');
    }
  }
}
</script>

<style>
.textInputDark{
  background-color: ghostwhite;
  width: 90%;
  height: 40%;
  margin-bottom: 5%;
  margin-top: 2%;
  border-width: 1px;
  border-color: #152679;
  align-self: center;
  color: ghostwhite;
}
</style>