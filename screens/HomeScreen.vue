<template>
  <view class="container">
    <text>This is the App Home screen</text>
    <button title="Go to home screen" @press="goToDetailsScreen"></button>
  </view>
</template>

<script>
export default {
  // Declare `navigation` as a prop
  props: {
    navigation: {
      type: Object
    }
  },
  methods: {
    goToDetailsScreen() {
      this.navigation.navigate("Details");
    }
  }
}
</script>