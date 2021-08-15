<template lang="html">
  <div class="px-12 md:px-40 lg:px-60 mt-16 md:mt-24 pb-16 md:pb-24">
    <div class="w-full">
      <div class="font-semibold my-10">
        <p class="mb-2 text-lg">Blog</p>
        <div class="boxShadow w-8 h-1 bg-black ml-1"></div>
      </div>
      <div class="grid gap-5 grid-cols-1 md:grid-cols-3">
        <div v-for="(blog, index) in blogs" :key="index" class="">
          <div class="bg-gray-50 hover:shadow-lg shadow-md w-full">
            <contentCard :item="blog" :index="blog" class="w-full"/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blogs: [
        {src: '/vercel.png', title: 'Deploy a Vue, Vite, and Tailwind project to Vercel', description: 'Learn how to set up your Vue, Vite, and Tailwind project and deploy it instantly on Vercel.', link: 'https://vercel.com/guides/vue-vite-tailwind', datePublished: 'July 11th 2021'},
        {src: '/nuxt-img.png', title: 'Optimize your images with Nuxt Image', description: 'Nuxt image handles the hard parts of transforming and optimizing assets through an intuitive interface. Let\'s learn how to use it!', link: '/blog-nuxt-image', datePublished: 'Aug 2nd 2021'},
        {src: '/petite-vue.webp', title: 'Vue vs petite-vue', description: 'petite-vue is a lightweight Vue alternative that can be “sprinkled” over your project requiring no extra bundling steps or build processes. Let\'s learn how to use it and compare it to standart Vue!', link: '/blog-petite-vue', datePublished: 'Aug 15th 2021'},
      ]
    }
  }
}
</script>

<style lang="css" scoped>
.d3 {
  font-weight: 800;
  color: rgb(30,30,30) ;
  text-transform: uppercase;
  letter-spacing: 0.053em;
  text-shadow: -0.07em 0 1px rgba(255,0,0,0.87), 0.07em 0 1px rgba(0, 255, 255, 0.87);
}
</style>
