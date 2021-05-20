<template>
  <div id="app">
    <div class="mall-container">
      <router-view/>
    </div>
    <main-tabbar/>
  </div>
</template>
<script>
import MainTabbar from "./components/content/mainTabBar/MainTabBar";

export default {
  name: "AppVue",
  components: {
    MainTabbar
  }
}
</script>
<style>
@import "assets/css/base.less";

#app {
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.mall-container {
  flex: 1;
}
</style>
