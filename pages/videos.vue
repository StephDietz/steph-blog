<template lang="html">
  <div class="px-12 md:px-40 lg:px-60 mt-16 md:mt-24 pb-16 md:pb-24">
    <h1 class="d3 text-4xl mb-12">Videos</h1>
    <div class="">
      <!-- <div class="font-semibold mb-10">
        <p class="mb-2 text-lg">Most Recent</p>
        <div class="boxShadow w-8 h-1 bg-black ml-1"></div>
      </div> -->
      <iframe height="315" class="w-full md:w-8/12" src="https://www.youtube.com/embed/ZRUhUZrTA2o" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
    <div class="w-full">
      <div class="font-semibold my-10">
        <p class="mb-2 text-lg">All Videos</p>
        <div class="boxShadow w-8 h-1 bg-black ml-1"></div>
      </div>
      <div class="grid gap-5 grid-cols-1 md:grid-cols-3">
        <div v-for="(video, index) in videos" :key="index" class="">
          <div class="bg-gray-50 hover:shadow-lg shadow-md w-full">
            <contentCard :item="video" :index="index" class="w-full"/>
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
      videos: [
        {src: '/nuxt-img-YT.png', title: 'Optimizing Images in my Nuxt/Vue Blog!', description: 'In this video, we will learn how to use Nuxt Image in a Nuxt app (and deploy it with Vercel!)', link: 'https://youtu.be/ZRUhUZrTA2o', datePublished: 'Aug 3rd 2021'},
        {src: '/youtube.png', title: 'Set up a new Vue 3 project with Vite and Tailwind (Deploy to Vercel!)', description: 'Learn how to create a new Vue 3 project with Vite, install Tailwind, and deploy our project to Vercel! I’ll take you through every step from start to finish.', link: 'https://www.youtube.com/watch?v=ftT8nHHCZrI&t=2s', datePublished: 'July 20th 2021'},
        {src: '/pinterestClone.jpg', title: 'Build a Pinterest clone with vue.js and tailwind.css', description: 'Learn how to use tailwind.css and vue.js to build a Pinterest clone!', link: 'https://youtu.be/aL28CSfKIww', datePublished: 'May 19th 2021'},
        {src: '/tailwindTheme.png', title: 'Customize tailwind.css theme', description: 'A complete tutorial to creating custom Tailwind CSS themes.', link: 'https://youtu.be/v9vcWt5us-Y', datePublished: 'May 18th 2021'},
        {src: '/tailwindTheme.png', title: 'Customize tailwind.css theme', description: 'A complete tutorial to creating custom Tailwind CSS themes.', link: 'https://youtu.be/v9vcWt5us-Y', datePublished: 'May 18th 2021'},
        {src: '/createTailwindVue.png', title: 'Set up a New Project with Vue.js and tailwind.css', description: 'A short tutorial explaining how to create a new project with vue.js and tailwind.css!', link: 'https://youtu.be/i6vQrVOoAJc', datePublished: 'Oct 16th 2020'},
        {src: '/webflow.png', title: 'Comparison between Webflow and coding', description: 'In this video I create two identical websites: one using webflow, the other coding it utilizing tailwindUI. I go over which one is quicker, which is better, and the overall pros and cons of each.', link: 'https://youtu.be/i9dT4odmX8A', datePublished: 'May 18th 2020'},
        {src: '/cardGame.png', title: 'Code a card game!!', description: 'Learn how to create a card drinking game that you can play with your friends over zoom!', link: 'https://youtu.be/Wpir1cf1l7c', datePublished: 'May 8th 2020'},
        {src: '/twitter.png', title: 'Build a twitter clone using vue.js and tailwind css!', description: 'In this video I recreate the twitter home page using vue.js and tailwind css!', link: 'https://youtu.be/bQU-jPyQJ4A', datePublished: 'May 1st 2020'},
        {src: '/selfTaught.png', title: 'Becoming a Self Taught Developer', description: 'In this video I tell my experience becoming a self taught developer, and the advice I\'d give to anyone who wants to start learning.', link: 'https://youtu.be/JRrza-FHLD4', datePublished: 'Apr 24th 2020'},
        {src: '/spotifyWebflow.png', title: 'Using Webflow to Clone the Spotify Home Page', description: 'Recreate Spotify\'s home page using Webflow!', link: 'https://youtu.be/xTgOVTydh3M', datePublished: 'Mar 25th 2020'},
        {src: '/spotify.png', title: 'Build a Spotify home page using tailwind.css and Vue.js', description: 'In this video, we will recreate the Spotify home page using tailwind.css and Vue.js and will add functionality to play one song.', link: 'https://youtu.be/w5GQcHxJH1w', datePublished: 'Feb 26th 2020'},

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
.boxShadow {
  box-shadow: -4px 0 rgba(255,0,0,0.87), 2px 2px  rgba(0, 255, 255, 0.87);
}
</style>
