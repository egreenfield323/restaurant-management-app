<template>
  <router-view />
</template>

<script>

export default {
  name: 'App',
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  padding: 0;
  margin: 0;
}

.logo {
  width: 150px
}

.register input,
.login input,
.add input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  display: block;
  margin: auto auto 30px auto;
  border: 1px solid rgb(0, 0, 82);
  border-radius: 25px;
}

.register button,
.login button,
.add button {
  width: 130px;
  height: 40px;
  border: 1px solid rgb(0, 0, 82);
  background-color: rgb(0, 0, 82);
  color: #fff;
  cursor: pointer;
  border-radius: 25px;
}

.register button:hover,
.login button:hover,
.add button:hover {
  width: 128px;
  background-color: rgb(0, 0, 21);
  border: 3px solid white;
}
</style>
