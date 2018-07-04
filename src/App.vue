<template>
<div id="app">
  <nav role="navigation" class="nav">
    <button class="hamburger" @click="toggleClass()">
      <div class="hamburger__line" v-bind:class="[isActive ? 'open' : '']"></div>
    </button>
    <ul class="menu-list" v-bind:class="[isActive ? 'menu-list--open' : '']">
      <li class="menu-list__item">
        <a class="menu-list__link" href="#start">Start</a>
      </li>
      <li class="menu-list__item">
        <a class="menu-list__link" href="#technologies">Technologie</a>
      </li>
      <li class="menu-list__item">
        <a class="menu-list__link" href="#projects">Projekty</a>
      </li>
      <li class="menu-list__item">
        <a class="menu-list__link" href="#contact">Kontakt</a>
      </li>
    </ul>
  </nav>
  <Home msg="Sabina Smalec" />
  <Technologies msg="Technologie"/>
  <Projects msg="Projekty" />
  <Contact msg="Kontakt" />
  <footer class="footer">
    <p class="mario-world-font">acamaabaialajijijaada aoaefghaapaak</p>
    <p>2018 | Sabina Smalec</p>
  </footer>
</div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Home from './components/Home.vue'
import Technologies from './components/Technologies.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Home,
    Technologies,
    Projects,
    Contact
  },
  data: function() {
    return {
      isActive: false
    }
  },
  methods: {
    toggleClass: function () {
      this.isActive ? this.isActive = false : this.isActive = true;
    }
  }
}
</script>

<style lang="scss">
.mario-world-font {
  font-family: 'MarioFont';
  line-height: 3.5em;
}
.footer {
  background: #ecf0f1;
  overflow: hidden;
  text-align: center;
  padding: 1rem 0;
}
</style>
