<template>
  <li class="gallery-menu__item"
      v-bind:class="{activeLeft: item.activeLink}"
      v-on:click="onClick() + $emit('reverse', index)"
  >
    <a href="#" class="gallery-menu__link">{{ item.title | uppercase}}</a>
    ({{ item.number }})
  </li>
</template>

<script>
export default {
  name: "MenuItem",

  props: {
    item: {
      type: Object
    },

    index: {
      type: Number
    }
  },

  filters: {
    uppercase(value) {
      return value.toUpperCase()
    }
  },

  methods: {
    onClick() {
      this.item.activeLink = true
    }
  }
}
</script>

<style scoped>
.gallery-menu__item {
  position: relative;
  display: flex;
  border-right: 1px solid #c4c4c4;
  padding: 0 12px 0 12px;
  font-size: 14px;
  line-height: 132.5%;
  letter-spacing: 0.18em;
}

.gallery-menu__item:nth-child(4) {
  border: none;
}

.gallery-menu__item.activeLeft::before {
  content: '';
  position: absolute;
  top: 28px;
  left: 0;
  width: 100%;
  height: 3px;
  background: #e14313;
}

.gallery-menu__link.activeLeft {
  color: #e14313;
}

.gallery-menu__link {
  text-decoration: none;
  color: #000;
  margin-right: 3px;
}

.gallery-menu__link:hover {
  color: lightsalmon;
}

</style>