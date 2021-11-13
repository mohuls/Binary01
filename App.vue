<template>
  <app-navigator></app-navigator>
</template>

<script>
// for moving between screens
import {
  createAppContainer,
  createStackNavigator,
} from "vue-native-router";

// components
import HomeScreen from './screens/HomeScreen.vue'
import DetailsScreen from './screens/DetailsScreen.vue'

const StackNavigator = createStackNavigator(
  {
    Home: HomeScreen,
    Details: DetailsScreen,
  },
  {
    initialRouteName: 'Home',
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: {
    AppNavigator,
  },

  data: function() {
    return {
      // data goes here
    };
  },
  methods: {
    // methods goes here
  }
};
</script>



<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-container {
  color: blue;
  padding: 2;
  font-size: 20;
}
</style>