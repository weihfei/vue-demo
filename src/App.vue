<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
      <router-link to="/toDoList">toDoList</router-link>
    </div> -->
    <h1>To Do List</h1>
    <div class="content-box">
      <router-view/>
    </div>
  </div>
</template>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

h1{
  margin: 50px auto 0;
  font-size: 60px;
  line-height: 60px;
  border-bottom: 1px solid #cccccc;
  padding-bottom: 20px;
  color: #7e7e7e;
}

.content-box{
  width: 90%;
  margin: 20px auto 0;
}
</style>
