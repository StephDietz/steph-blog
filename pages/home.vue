<template>
  <div class="">
    <pageHeader :menuItems="menuItems"/>
    <nuxt />
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
