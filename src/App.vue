<template>
  <div id="app">

    <galleryMenu
        v-bind:menu="menu"
        v-on:reverse-true="reverseTrue"
    />

  </div>
</template>

<script>
import galleryMenu from './components/GalleryMenu'

export default {
  name: 'App',
  components: {
    galleryMenu
  },

  data() {
    return {
      menu : [
        {id: 1, title: 'архитектура', number: 12, activeLink: true},
        {id: 2, title: 'инфраструктура', number: 2, activeLink: false},
        {id: 3, title: 'интерьер', number: 31, activeLink: false},
        {id: 4, title: 'лобби', number: 1, activeLink: false}
        ]
    }
  },

  methods: {
    reverseTrue(index) {
        console.log(index)



    }
  }
}
</script>

<style>
@font-face {
  font-family: 'Bebas Neue';
  src: url('./assets/fonts/Bebas Neue.eot');
  src: local('☺'), url('./assets/fonts/Bebas Neue.woff') format('woff'), url('./assets/fonts/Bebas Neue.ttf') format('truetype'), url('./assets/fonts/Bebas Neue.svg') format('svg');
  font-weight: normal;
  font-style: normal;
}

#app {
  font-family: 'Bebas Neue', cursive;
  color: #18181b;
  background: #111111;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

* {
  margin: 0;
  padding: 0;
}
</style>
