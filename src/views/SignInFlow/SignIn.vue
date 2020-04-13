<template>
  <div
    class="container"
    :class="{ 'light-background': !isDarkMode, 'dark-background': isDarkMode }"
  >
    <div
      class="request"
      :class="{ 'light-request': !isDarkMode, 'dark-request': isDarkMode }"
    >
      没有账户？
      <router-link to="/request">点此创建</router-link>
    </div>
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
      <button @click="toggleDarkMode">切换显示模式</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignIn",
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    }
  },
  methods: {
    toggleDarkMode() {
      this.$store.commit("toggleDarkMode");
    }
  }
};
</script>

<style lang="scss" scoped>
.light-background {
  background-color: $light-gray;
}

.dark-background {
  background-color: $dark-blue;
}

.light-text {
  color: $black;
}

.dark-text {
  color: $white;
}

.light-field {
  background-color: rgba(198, 208, 235, 0.2);
  border: 1px solid rgba(19, 16, 16, 0.2);

  &::placeholder {
    color: rgba(0, 0, 0, 0.3);
  }
}

.dark-field {
  background-color: rgba(255, 255, 255, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.2);

  &::placeholder {
    color: rgba(255, 255, 255, 0.3);
  }
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;

  min-height: 100vh;
}

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

.login {
  width: 400px;

  img {
    width: 120px;
    height: 120px;
  }
}

h4 {
  margin: 0;
  font-size: 24px;
  line-height: 34px;
  text-align: center;

  color: #ffffff;
}

input {
  margin-top: 20px;
  padding: 0 20px;
  background-color: rgba(255, 255, 255, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.2);
  box-sizing: border-box;
  border-radius: 6px;

  &::placeholder {
    color: rgba(255, 255, 255, 0.3);
  }

  &:focus {
    outline: none;
  }

  height: 60px;
  width: 100%;

  font-size: 20px;
  color: white;
}

button {
  background-color: #56ccf2;
  box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.2);
  border-radius: 6px;
  border: none;
  margin-top: 20px;
  margin-bottom: 20px;

  &:focus {
    outline: none;
  }

  &:hover {
    background-color: #41a7c9;
  }

  &:active {
    background-color: #207c9b;
  }

  height: 60px;
  width: 100%;

  font-size: 20px;
  color: #ffffff;
}

a {
  line-height: 25px;
  font-size: 16px;
  text-align: center;
  text-decoration: none;
}

.light-recover {
  color: rgba(0, 0, 0, 0.3);
}

.dark-recover {
  color: rgba(255, 255, 255, 0.3);
}
</style>
