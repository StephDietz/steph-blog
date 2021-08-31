<template lang="html">
  <a :href="`${item.link}`" target="_blank">
    <div>
      <div class="block overflow-hidden relative w-full h-40 bg-center bg-cover" :style="`background-image: url(${item.src})`">
        <!-- <nuxt-img
          :src="`${item.src}`"
          sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
          alt="blogImage"
          class="img rounded z-10"/> -->
      </div>
      <div class="p-4">
        <h1 class="clamp-2 font-bold h-10 mb-1 leading-tight"> {{ item.title }} </h1>
        <h2 class="clamp-3 h-12 text-sm leading-tight"> {{ item.description }} </h2>
        <div class="flex justify-between items-center text-xs font-medium my-3">
          <div :class="`bg-gray-300 rounded-full px-3 py-1`">{{type}}</div><div>{{ item.datePublished }}</div>
        </div>
      </div>
    </div>
  </a>
</template>

<script>
export default {
  props: ['item', 'index', 'type']
}
</script>

<style lang="css" scoped>
.clamp-3 {
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
}
.clamp-2 {
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
.img {
  pointer-events: none;
  position: absolute;
  width: 100%;
  height: 100%;
}

</style>
