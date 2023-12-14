<template>
  <Home/>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

*,
*::before,
*::after {
    box-sizing: border-box;
}

body,
h1,
h2,
h3,
p {
    margin: 0;
}

ul {
    margin: 0;
    padding: 0;
}

:root {
    --white: #FFFFFF;
    --blue: #28b3fa;
}

html {
    font-size: 62.5%;
}

body {
  font-family: 'Poppins', sans-serif;
}
</style>
