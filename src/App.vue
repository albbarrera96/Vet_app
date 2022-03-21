<template>
  <Navbar />
  <Intro />
  <Prices />
  <Accordion />
  <Contact />
  <List/>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Intro from './components/section1.vue'
import Prices from './components/section2.vue'
import Accordion from './components/section3.vue'
import Contact from './components/section4.vue'
import List from './components/section5.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Intro,
    Prices,
    Accordion,
    Contact,
    List
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
