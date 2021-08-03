<template lang="html">
  <div class="px-12 md:px-40 lg:px-60 mt-16 md:mt-24 pb-16 md:pb-24">
    <h1 class="d3 text-4xl mb-12">Blog</h1>
    <div class="flex">
      <div v-for="(blog, index) in blogs" :key="index" :class="`${index % 2 ? 'md:mx-6' : ''} w-full md:w-1/3 my-6 bg-gray-50 hover:shadow-lg shadow-md`">
        <contentCard :item="blog" :index="index" />
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
