<template>
  <tabbar>
    <tabbar-item
        v-for="(item,index) in tabbarList"
        :key="item.key"
        :path="item.path"
    >
      <template #slot-icon>
        <i :class="item.iconClass"/>
      </template>
      <template #slot-text>
        {{ item.title }}
      </template>
    </tabbar-item>
  </tabbar>
</template>

<script>
import Tabbar from "../../common/tabbar/Tabbar";
import TabbarItem from "../../common/tabbar/TabbarItem";

export default {
  name: "MainTabbar",
  data() {
    return {
      tabbarList: [{
        title: '首页',
        key: 'index',
        iconClass: 'el-icon-s-home',
        path: '/home'
      }, {
        title: '分类',
        key: 'category',
        iconClass: 'el-icon-menu',
        path: '/category'
      }, {
        title: '购物车',
        key: 'cart',
        iconClass: 'el-icon-s-goods',
        path: '/cart'
      }, {
        title: "我的",
        key: 'profile',
        iconClass: 'el-icon-user-solid',
        path: '/profile'
      }],
    }
  },
  components: {
    Tabbar,
    TabbarItem
  }
}
</script>

<style scoped>

</style>