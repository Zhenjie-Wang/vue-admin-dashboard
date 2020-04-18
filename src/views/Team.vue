<template>
  <div class="container">
    <h2>Team</h2>
    <div class="cards">
      <transition appear appear-active-class="animated flipInX">
        <a
          class="card card-1"
          :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ></a>
      </transition>
      <transition appear appear-active-class="animated flipInX">
        <a
          class="card card-2"
          :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ></a>
      </transition>
      <transition appear appear-active-class="animated flipInX">
        <a
          class="card card-3"
          :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ></a>
      </transition>
      <transition appear appear-active-class="animated flipInX">
        <a
          class="card card-4"
          :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ></a>
      </transition>
      <transition appear appear-active-class="animated flipInX">
        <a
          class="card card-5"
          :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ></a>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: "Team",
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    }
  }
};
</script>

<style scope lang="scss">
.container {
  margin: 0 25px;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: space-evenly;
}

.card {
  height: 50px;
  width: 50px;
  background-color: red;
  margin: 20px;
}

.card-1 {
  animation-delay: 0;
}

.card-2 {
  animation-delay: 0.5s;
}

.card-3 {
  animation-delay: 1s;
}

.card-4 {
  animation-delay: 1.5s;
}

.card-5 {
  animation-delay: 2s;
}

.light-card {
  background-color: $white;
}

.dark-card {
  background-color: $super-dark-blue;
}
</style>
