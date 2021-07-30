<template lang="html">
  <div class="w-full py-4 px-12 md:px-40 lg:px-60 border-b flex items-center">
    <div class="hidden w-1/3 lg:flex items-center">
      <a href="https://twitter.com/steph_dietz_" target="_blank" class="mr-10">
        <nuxt-img
          src="/twitter-brands.svg"
          sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
          alt="twitter"
          class="h-5"/>
      </a>
      <a href="https://github.com/StephDietz" target="_blank" class="mr-10">
        <nuxt-img
          src="/github-brands.svg"
          sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
          alt="twitter"
          class="h-5"/>
      </a>
      <a href="https://www.youtube.com/channel/UCr8BLoBSZtmVr31UEfCiQfA" target="_blank" class="mr-10">
        <nuxt-img
          src="/youtube-brands.svg"
          sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
          alt="twitter"
          class="h-5"/>
      </a>
    </div>
    <div class="d3 flex-none md:text-xl lg:w-1/3 flex items-center justify-center uppercase font-semibold tracking-widest">
      <NuxtLink :to="`/`">Steph Dietz</NuxtLink>
    </div>
    <div class="lg:w-1/3 ml-auto lg:ml-0 flex items-center justify-end font-semibold">
      <div v-for="(item, index) in menuItems" class="ml-3 md:ml-10 link text-xs md:text-base">
        <NuxtLink :to="`/${item.path}`"> {{ item.name }} </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['menuItems']
}
</script>

<style lang="css" scoped>
@import url('https://fonts.googleapis.com/css?family=Abril+Fatface|Anton|Marcellus+SC|Shrikhand&display=swap');

.d3 {
  margin: 0.5em 0;
  color: rgb(30,30,30) ;
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 0.053em;
  text-shadow: -0.07em 0 1px rgba(255,0,0,0.87), 0.07em 0 1px rgba(0, 255, 255, 0.87);
}
.link:hover {
  color: rgb(30,30,30) ;
  text-shadow: -0.07em 0 1px rgba(255,0,0,0.87), 0.07em 0 1px rgba(0, 255, 255, 0.87);
}
</style>
