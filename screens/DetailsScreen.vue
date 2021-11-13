<template>
  <view class="container but">
    <text>This is the App Details screen!!</text>
    <button title="Go to home screen" @press="goToHomeScreen"></button>
    <button class="text" title="Store data" @press="storeData('Store again')"></button>
    <touchable-opacity class="bt" :on-press="getData">
      <text class="btxt">Hello</text>
    </touchable-opacity>
    <text class="text">{{text}}</text>


    <text-input
      :style="{height: 40, width: 200, borderColor: 'gray', borderWidth: 2, padding: 10, marginLeft: 100, borderColor: 'red', backgroundColor: 'red', color: 'wheat', fontSize: 20}"
      v-model="text"
    />
  </view>
</template>

<script>
import AsyncStorage from '@react-native-async-storage/async-storage';

import Signup from './Signup.vue'

export default {
  components: {
    Signup
  },
  // Declare `navigation` as a prop
  props: {
    navigation: {
      type: Object
    }
  },
  data: function() {
    return {
      datas: '',
      text: 'hello'
    }
  },
  methods: {
    goToHomeScreen() {
      this.navigation.navigate("Home");
    },
    storeData: async (value) => {
      try {
        await AsyncStorage.setItem('id', value)
        alert("Data stored")
      } catch (e) {
        alert("Failed to store data")
      }
    },
    getData: async () => {
      try {
        const value = await AsyncStorage.getItem('id')
        if(value !== null) {
          alert(value)
        }
      } catch(e) {
        alert(e)
      }
    }

  }
}
</script>
<style>
.bt {
  background-color: red;
  width: 100px;
  text-align: center;
  color: white;
}
.btxt {
  color: wheat;
  text-align: center;
  padding: 10px;
}
</style>