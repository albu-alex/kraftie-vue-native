<template>
 <app-navigator></app-navigator>
</template>

<script>
import {
  createAppContainer,
  createBottomTabNavigator,
} from "vue-native-router";
import {FontAwesome5} from "@expo/vector-icons";
import HomePage from "./HomePage";
import Search from "./Search";
import Profile from "./Profile";
import Kart from "./Kart"
import React from 'react';
const BottomTabNavigator = createBottomTabNavigator(
    {
      Acasă: {
        screen: HomePage,
        navigationOptions: {
          title: 'Acasă',
          tabBarIcon: <FontAwesome5 name="home" color={'#152679'} size={25}/>,
          activeTintColor: '#2CA6A4',
        },
      },
      Caută: {
        screen: Search,
        navigationOptions: {
          title: 'Caută',
          tabBarIcon: <FontAwesome5 name="search" color={'#152679'} size={25}/>,
          activeTintColor: '#2CA6A4',
        },
      },
      Kart: {
        screen: Kart,
        navigationOptions: {
          title: 'Coș',
          tabBarIcon: <FontAwesome5 name="shopping-bag" color={'#152679'} size={25}/>,
          activeTintColor: '#2CA6A4'
        }
      },
      Profil: {
        screen: Profile,
        navigationOptions: {
          title: 'Profil',
          tabBarIcon: <FontAwesome5 name="user" color={'#152679'} size={25}/>,
          activeTintColor: '#2CA6A4'
        }
      }
    },
    {
      tabBarOptions:{
        inactiveTintColor: "#152679",
        activeTintColor: "#2CA6A4",
      }
    }
);
const AppNavigator = createAppContainer(BottomTabNavigator);
export default {
  name: "HomeScreen",
  components:{
    AppNavigator,
    FontAwesome5
  }
}
</script>

<style>
.mainText{
  font-size: 20px;
}
</style>