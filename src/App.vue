<template>
    <div id="nav">
      <router-link to="/">1  </router-link>
      <router-link to="/about">  2</router-link>
    </div>
  <router-view/>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  position: absolute;
  transform: translateY(400px);
  padding: 30px;
  width: 1860px;
  background-color: white;
  opacity: 0.8;
  text-align: right;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
