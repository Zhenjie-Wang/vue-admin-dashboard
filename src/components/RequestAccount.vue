<template>
  <transition name="slide-in-right" enter-active-class="animated slideInRight">
    <div
      class="request"
      :class="{ 'light-request': !isDarkMode, 'dark-request': isDarkMode }"
      v-show="show"
    >
      没有账户？
      <router-link to="/request">点此创建</router-link>
    </div>
  </transition>
</template>

<script>
export default {
  name: "RequestAccount",
  data: function() {
    return {
      show: false
    };
  },
  mounted() {
    this.show = true;
  },
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    }
  }
};
</script>

<style lang="scss" scoped>
.request {
  position: absolute;
  top: 20px;
  right: 30px;
}

.light-request {
  color: rgba(0, 0, 0, 0.3);

  a {
    color: #000000;
  }
}

.dark-request {
  color: rgba(255, 255, 255, 0.3);

  a {
    color: #ffffff;
  }
}
</style>
