<template>
  <view :style="{backgroundColor: 'ghostwhite', flex: 1}">
    <Header color="ghostwhite" />
    <view class="searchHeader">
      <Ionicons :style="{paddingLeft: 10, zIndex: 2, paddingTop: 25}" name="ios-search-outline" :size=24 color="#152679" />
      <text-input :autoCorrect="false" placeholderTextColor="#152679" :style="{paddingVertical: 10, borderRadius: 10, paddingHorizontal: 25, marginLeft: -40}"
                  placeholder="Caută ceea ce dorești" class="textInputDark" v-model="searchText"
                  keyboardAppearance="dark"></text-input>
      <touchable-opacity :style="{borderRadius: 10, marginTop: 28}" :on-press="cancelSearch">
        <text class="buttonTextDark">Cancel</text>
      </touchable-opacity>
    </view>
    <scroll-view>
      <view v-if="showResults" v-for="(product, index) in results">
        <ProductLandscape :post-number="index + 1" :description="results[index]" class="productLandscape" />
      </view>
    </scroll-view>
  </view>
</template>

<script>
import Header from "./Header";
import {Ionicons} from '@expo/vector-icons'
import ProductLandscape from "./ProductLandscape";
export default {
  beforeUpdate(){
    if(this.searchText === 'festive'){
      this.results.push("Globuri de craciun rosii")
      this.results.push("Set Globuri de Craciun Multicolore")
      this.results.push("Set globuri Craciun, pentru brad, din plastic")
      this.results.push("Set globuri pentru Craciun mov cu sclipici")
      this.results.push("Set 4 globuri pentru Craciun handmade")
      this.searchText = "";
      this.showResults = true;
    }
  },
  data(){
    return{
      searchText: "",
      results: [],
      showResults: false
    }
  },
  name: "Search",
  components:{
    ProductLandscape,
    Header,
    Ionicons
  },
  props:{
    navigation:{
      type: Object
    }
  },
  methods:{
    cancelSearch(){
      this.navigation.navigate('Acasă')
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
.textInputDark{
  background-color: ghostwhite;
  width: 80%;
  height: 50%;
  margin-bottom: 5%;
  margin-top: 5%;
  border-width: 1px;
  border-color: #152679;
  align-self: center;
  color: #152679;
}
.searchHeader{
  margin-top: 3%;
  flex-direction: row;
  justify-content: space-between;
}
.buttonTextDark{
  color: #E3170A;
  font-size: 16px;
  font-weight: 500;
  margin-right: 2%;
}
</style>