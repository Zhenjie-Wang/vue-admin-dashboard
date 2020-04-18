<template>
  <div
    class="container"
    :class="{ 'light-background': !isDarkMode, 'dark-background': isDarkMode }"
  >
    <RequestAccount />
    <div class="login">
      <img src="@/assets/logo-light.png" v-show="!isDarkMode" />
      <img src="@/assets/logo-dark.png" v-show="isDarkMode" />
      <h4 :class="{ 'light-text': !isDarkMode, 'dark-mode': isDarkMode }">
        登录到Vue
      </h4>
      <input
        type="email"
        placeholder="请输入邮箱地址"
        :class="{ 'light-field': !isDarkMode, 'dark-field': isDarkMode }"
      />
      <input
        type="password"
        placeholder="请输入密码"
        :class="{ 'light-field': !isDarkMode, 'dark-field': isDarkMode }"
      />
      <button>登录</button>
      <router-link
        to="/recover"
        :class="{ 'light-recover': !isDarkMode, 'dark-recover': isDarkMode }"
        >忘记密码？</router-link
      >
      <ThemeSwitch />
    </div>
  </div>
</template>

<script>
import RequestAccount from "@/components/RequestAccount.vue";
import ThemeSwitch from "@/components/ThemeSwitch.vue";

export default {
  name: "SignIn",
  components: {
    RequestAccount,
    ThemeSwitch
  },
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    }
  }
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;

  min-height: 100vh;
}

.login {
  width: 400px;

  img {
    width: 120px;
    height: 120px;
  }
}
</style>
