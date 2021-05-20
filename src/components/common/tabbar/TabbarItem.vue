<template>
  <div :class="['tabbar-item',{'tabbar-item-active':isActive}]" @click="isActive ? null : itemClick()">
    <div class="tabbar-img">
      <slot name="slot-icon"></slot>
    </div>
    <div class="tabbar-text">
      <slot name="slot-text"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabbarItem",
  props: {
    path: {
      type: String
    }
  },
  computed: {
    isActive() {
      return this.$route.path.indexOf(this.path) !== -1
    }
  },
  methods: {
    itemClick() {
      this.$router.push(this.path)
    }
  },
}
</script>

<style scoped>
.tabbar-item {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  flex: 1;
}

.tabbar-item-active {
  color: red;
}

.tabbar-img > i {
  font-size: 20px;
}
</style>