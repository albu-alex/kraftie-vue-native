<template>
  <view v-if="!showRegister" :style="{backgroundColor: 'ghostwhite', flex: 1}">
    <Header color="ghostwhite" />
    <text :style="{marginTop: 50}" class="mainText">Ups... Se pare că nu ai cont</text>
    <touchable-opacity :style="{borderRadius: 7, paddingHorizontal: 20}" class="payButton" :onPress="becomeSeller">
      <text class="buttonText">Alătură-te cumpărătorilor</text>
    </touchable-opacity>
    <touchable-opacity :style="{borderRadius: 7, paddingHorizontal: 20}" class="payButton1" :onPress="becomeBuyer">
      <text class="buttonText">Alătură-te vânzătorilor</text>
    </touchable-opacity>
  </view>
  <view v-else :style="{backgroundColor: 'ghostwhite', flex: 1}">
    <Header color="ghostwhite" />
     <FontAwesome5 :style="{paddingLeft: 25, zIndex: 2, paddingTop: 28}" name="user" :size=20 color="#152679" />
     <text-input :autoCorrect="false" placeholderTextColor="#152679" :style="{paddingVertical: 10, borderRadius: 10, paddingHorizontal: 25, marginLeft: -5}"
                placeholder="Nume utilizator" class="textInputDark"
                keyboardAppearance="dark"></text-input>
    <FontAwesome5 :style="{paddingLeft: 25, zIndex: 2, paddingTop: 28}" name="mail-bulk" :size=16 color="#152679" />
    <text-input :autoCorrect="false" placeholderTextColor="#152679" :style="{paddingVertical: 10, borderRadius: 10, paddingHorizontal: 25, marginLeft: -5}"
                placeholder="Email" class="textInputDark"
                keyboardAppearance="dark"></text-input>
    <FontAwesome5 :style="{paddingLeft: 25, zIndex: 2, paddingTop: 28}" name="hashtag" :size=20 color="#152679" />
    <text-input :autoCorrect="false" placeholderTextColor="#152679" :style="{paddingVertical: 10, borderRadius: 10, paddingHorizontal: 25, marginLeft: -5}"
                placeholder="Parola" class="textInputDark"
                keyboardAppearance="dark"></text-input>
    <touchable-opacity :activeOpacity="0.5" :style="{borderRadius: 7, paddingHorizontal: 20}" class="payButton2" :onPress="becomeSeller">
      <text class="buttonText">Înregistrează-te</text>
    </touchable-opacity>
    <view class="loginWithServices">
      <touchable-opacity :style="{marginLeft: 12}" :on-press="doNothing">
        <FontAwesome5 name="facebook" :size=60 color="#0044FF" />
      </touchable-opacity>
      <touchable-opacity :on-press="doNothing">
        <FontAwesome5 class="logoGoogle" name="google-plus-square" :size=60 color="red" />
      </touchable-opacity>
      <touchable-opacity :on-press="doNothing">
        <FontAwesome5 name="apple" :size=60 color="#070000" />
      </touchable-opacity>
    </view>
  </view>
</template>

<script>
import Header from "./Header";
import {FontAwesome5} from "@expo/vector-icons";
export default {
  name: "Profile",
  components:{
    Header,
    FontAwesome5
  },
  data(){
    return{
      showRegister: false
    }
  },
  methods:{
    becomeSeller(){
      this.showRegister = true;
    },
    becomeBuyer(){
      this.showRegister = true;
    },
    doNothing(){

    }
  }
}
</script>

<style>
.logoGoogle{
  margin-left: 25%;
  margin-right: 25%;
  align-self: center;
}
.mainText{
  color: #152679;
  align-self: center;
  font-weight: bold;
  font-size: 26px;
  margin-top: 4%;
  margin-bottom: 4%;
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
.payButton1{
  margin-top: 5%;
  background-color: #2CA6A4;
  align-self: center;
  align-items: center;
  align-content: center;
  height: 5%;
  width: 80%;
  border-width: 1px;
}
.payButton2{
  margin-top: 35%;
  background-color: #2CA6A4;
  align-self: center;
  align-items: center;
  align-content: center;
  height: 5%;
  width: 80%;
  border-width: 1px;
}
.buttonText{
  margin-top: 7px;
  color: #152679;
  align-self: center;
  justify-content: center;
  font-weight: 400;
  font-size: 20px;
}
.textInputDark{
  background-color: ghostwhite;
  width: 90%;
  height: 5%;
  margin-bottom: 5%;
  margin-top: -7%;
  border-width: 1px;
  border-color: #152679;
  align-self: center;
  color: #152679;
}
.loginWithServices{
  margin-top: 25%;
  flex-direction: row;
}
</style>