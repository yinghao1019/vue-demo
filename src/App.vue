<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about?x=aaa">About</router-link>
    <ul>
      <li v-for="i in 5" :key="i">
        <router-link :to="`/users/${i}`"> /users/{{ i }} </router-link>
      </li>
    </ul>
  </nav>
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

ul {
  display: inline-flex;
  margin: 5px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
