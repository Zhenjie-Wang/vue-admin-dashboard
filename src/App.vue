<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
import "animate.css";

export default {
  name: "app",
  mounted() {
    const isDarkMode = this.$store.getters.isDarkMode;
    document.body.style.backgroundColor = isDarkMode ? "#212c4f" : "#f0f3f5";
  }
};
</script>

<style lang="scss">
* {
  transition: cubic-bezier(0.2, 0.8, 0.2, 1) 0.8s;
}

body {
  background-color: $dark-blue;
  // margin: 0;
  // padding: 0;
}

#app {
  font-family: $system-font-family;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: $white;
}

h1 {
  @include heading-1;
}

p {
  @include large-text-bold($purple);
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: $white;

    &.router-link-exact-active {
      color: #42b983;
    }
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

/* Theme */
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

.light-recover {
  color: rgba(0, 0, 0, 0.3);
}

.dark-recover {
  color: rgba(255, 255, 255, 0.3);
}
</style>
