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
  text-align: center;
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
</style>
