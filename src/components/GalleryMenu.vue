<template>
<div>
  <ul class="gallery-menu">
    <item
        v-for="(menuItems, index) of menu"
        :key="menuItems.id"
        v-bind:item="menuItems"
        v-bind:index="index"
        v-on:reverse="reverseTrue"
    />
  </ul>
</div>
</template>

<script>
import item from '@/components/MenuItem'

export default {
name: "GalleryMenu",

  props: ['menu'],

  components: {
  item
  },

  methods: {
  reverseTrue(index) {
    this.$emit('reverse-true', index)

  }
  }
}
</script>

<style scoped>
.gallery-menu {
  display: flex;
  justify-content: center;
  list-style: none;
  width: 100%;
  padding: 13px 0 13px 0;
  background: #fff;
}
</style>