<template>
  <div class="">
    <pageHeader :menuItems="menuItems" class="sticky top-0 bg-white bg-opacity-95 z-50"/>
    <Nuxt class="templateContainer"/>
    <pageFooter />
  </div>
</template>

<script>

export default {
  data() {
    return {
      menuItems: [
        {name: 'About', path: 'about'},
        {name: 'Blog', path: 'blog'},
        {name: 'Videos', path: 'videos'}
      ]
    }
  }
}
</script>

<style media="screen">
.templateContainer {
  min-height: 65vh;
  }
</style>
