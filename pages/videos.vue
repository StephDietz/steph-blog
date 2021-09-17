<template lang="html">
  <div class="px-12 md:px-40 lg:px-60 mt-16 md:mt-24 pb-16 md:pb-24">
    <h1 class="d3 text-4xl mb-12">Videos</h1>
    <div class="">
      <!-- <div class="font-semibold mb-10">
        <p class="mb-2 text-lg">Most Recent</p>
        <div class="boxShadow w-8 h-1 bg-black ml-1"></div>
      </div> -->
      <iframe height="315" class="w-full md:w-8/12" src="https://www.youtube.com/embed/uC6y59y4V4w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
    <div class="w-full">
      <div class="font-semibold my-10">
        <p class="mb-2 text-lg">All Videos</p>
        <div class="boxShadow w-8 h-1 bg-black ml-1"></div>
      </div>
      <div class="grid gap-5 grid-cols-1 md:grid-cols-3">
        <div v-for="(video, index) in videos" :key="index" class="">
          <div class="bg-gray-50 hover:shadow-lg shadow-md w-full">
            <contentCard :item="video" :index="index" :type="video.type" class="w-full"/>
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
        {type: 'video', src: '/sveltekit-itunes.png', title: 'Intro to SvelteKit: Build an iTunes Search App!', description: 'Learn how to build an iTunes search app using SvelteKit! This is a beginner friendly tutorial that covers all the basics!', link: 'https://youtu.be/uC6y59y4V4w', datePublished: 'Sept 15th 2021'},
        {type: 'video', src: '/svelteVsVue.png', title: 'Svelte vs Vue: A Svelte crash course and analysis', description: 'A quick but complete look at how to use Svelte and how it compares to Vue! I  build a simple game app with Svelte and do a side-by-side comparison with Vue along the way.', link: 'https://youtu.be/JtQkCbUGPgA', datePublished: 'Aug 31st 2021'},
        {type: 'video', src: '/petite-vue.jpg', title: 'Building YouTube Search with Petite Vue! (5kb Vue Alternative)', description: 'petite-vue is a new lightweight framework that provides the same template syntax and reactivity mental model with standard Vue. In this tutorial I\'ll explain what petite-vue is, how to use it, and finally create a YouTube search app with it!', link: 'https://youtu.be/Y_g5-7NKp0A', datePublished: 'Aug 15th 2021'},
        {type: 'video', src: '/nuxt-img-YT.png', title: 'Optimizing Images in my Nuxt/Vue Blog!', description: 'In this video, we will learn how to use Nuxt Image in a Nuxt app (and deploy it with Vercel!)', link: 'https://youtu.be/ZRUhUZrTA2o', datePublished: 'Aug 3rd 2021'},
        {type: 'video', src: '/youtube.png', title: 'Set up a new Vue 3 project with Vite and Tailwind (Deploy to Vercel!)', description: 'Learn how to create a new Vue 3 project with Vite, install Tailwind, and deploy our project to Vercel! I’ll take you through every step from start to finish.', link: 'https://www.youtube.com/watch?v=ftT8nHHCZrI&t=2s', datePublished: 'July 20th 2021'},
        {type: 'video', src: '/pinterestClone.jpg', title: 'Build a Pinterest clone with vue.js and tailwind.css', description: 'Learn how to use tailwind.css and vue.js to build a Pinterest clone!', link: 'https://youtu.be/aL28CSfKIww', datePublished: 'May 19th 2021'},
        {type: 'video', src: '/tailwindTheme.png', title: 'Customize tailwind.css theme', description: 'A complete tutorial to creating custom Tailwind CSS themes.', link: 'https://youtu.be/v9vcWt5us-Y', datePublished: 'May 18th 2021'},
        {type: 'video', src: '/tailwindTheme.png', title: 'Customize tailwind.css theme', description: 'A complete tutorial to creating custom Tailwind CSS themes.', link: 'https://youtu.be/v9vcWt5us-Y', datePublished: 'May 18th 2021'},
        {type: 'video', src: '/createTailwindVue.png', title: 'Set up a New Project with Vue.js and tailwind.css', description: 'A short tutorial explaining how to create a new project with vue.js and tailwind.css!', link: 'https://youtu.be/i6vQrVOoAJc', datePublished: 'Oct 16th 2020'},
        {type: 'video', src: '/webflow.png', title: 'Comparison between Webflow and coding', description: 'In this video I create two identical websites: one using webflow, the other coding it utilizing tailwindUI. I go over which one is quicker, which is better, and the overall pros and cons of each.', link: 'https://youtu.be/i9dT4odmX8A', datePublished: 'May 18th 2020'},
        {type: 'video', src: '/cardGame.png', title: 'Code a card game!!', description: 'Learn how to create a card drinking game that you can play with your friends over zoom!', link: 'https://youtu.be/Wpir1cf1l7c', datePublished: 'May 8th 2020'},
        {type: 'video', src: '/twitter.png', title: 'Build a twitter clone using vue.js and tailwind css!', description: 'In this video I recreate the twitter home page using vue.js and tailwind css!', link: 'https://youtu.be/bQU-jPyQJ4A', datePublished: 'May 1st 2020'},
        {type: 'video', src: '/selfTaught.png', title: 'Becoming a Self Taught Developer', description: 'In this video I tell my experience becoming a self taught developer, and the advice I\'d give to anyone who wants to start learning.', link: 'https://youtu.be/JRrza-FHLD4', datePublished: 'Apr 24th 2020'},
        {type: 'video', src: '/spotifyWebflow.png', title: 'Using Webflow to Clone the Spotify Home Page', description: 'Recreate Spotify\'s home page using Webflow!', link: 'https://youtu.be/xTgOVTydh3M', datePublished: 'Mar 25th 2020'},
        {type: 'video', src: '/spotify.png', title: 'Build a Spotify home page using tailwind.css and Vue.js', description: 'In this video, we will recreate the Spotify home page using tailwind.css and Vue.js and will add functionality to play one song.', link: 'https://youtu.be/w5GQcHxJH1w', datePublished: 'Feb 26th 2020'},

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
