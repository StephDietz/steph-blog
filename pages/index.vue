<template>
  <div class="">
    <div class="flex md:flex-row flex-col px-12 md:px-40 lg:px-60 mt-16 md:mt-24 pb-16 md:pb-24 border-b">
      <div class="">
        <div class="d3 text-4xl md:text-6xl">
          Hey, I'm Steph.
        </div>
        <div class="md:text-xl md:mr-12">
          <div class="">
            I'm a self taught Frontend Developer learning software engineering by doing. Follow me on my journey to learn all the tips and tricks I pick up along the way :)
          </div>
          <div class="mt-6 mb-4">
            Let's stay in touch!
          </div>
          <div class="flex items-center">
            <a href="https://twitter.com/steph_dietz_" target="_blank" class="button mr-4 flex justify-center items-center w-10 h-10 bg-black text-white" style="border-radius: 999px;">
              <nuxt-img
                src="/twitter-brands.svg"
                sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
                alt="twitter"
                class="h-4"
                style="filter: invert(1);"/>
            </a>
            <a href="https://github.com/StephDietz" target="_blank" class="button mr-4 flex justify-center items-center w-10 h-10 bg-black text-white" style="border-radius: 999px;">
              <nuxt-img
                src="/github-brands.svg"
                sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
                alt="github"
                class="h-4"
                style="filter: invert(1);"/>
            </a>
            <a href="https://www.youtube.com/channel/UCr8BLoBSZtmVr31UEfCiQfA" target="_blank" class="button flex justify-center items-center w-10 h-10 bg-black text-white" style="border-radius: 999px;">
              <nuxt-img
                src="/youtube-brands.svg"
                sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
                alt="youtube"
                class="h-4"
                style="filter: invert(1);"/>
            </a>
          </div>
        </div>
      </div>
      <div class="flex-none mt-8">
        <div class="bg-center bg-cover w-48 h-48 mt-10 md:mt-0" style="border-radius: 999px; background-image: url(/profile.jpg)">
          <!-- <nuxt-img
            src="/profile.jpg"
            alt="profilePic"
            sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
            class="absolute"/> -->
        </div>
      </div>
    </div>

    <div class="px-12 md:px-40 lg:px-60 mb-16 md:mb-24 mt-16 md:mt-24">
      <div class="font-semibold mb-10">
        <p class="mb-2 text-lg">Recents</p>
        <div class="boxShadow w-8 h-1 bg-black ml-1"></div>
      </div>
      <div class="grid gap-5 grid-cols-1 md:grid-cols-3">
        <div v-for="(recent, index) in recents" :key="index" class="">
          <div class="bg-gray-50 hover:shadow-lg shadow-md w-full">
            <contentCard :item="recent" :index="index" :type="recent.type" class="w-full"/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  layout: 'home',
  data() {
    return {
      menuItems: [
        {name: 'About', path: 'about'},
        {name: 'Blog', path: 'blog'},
        {name: 'Videos', path: 'videos'}
      ],
      recents: [
        {type: 'blog', src: '/svelte-kit.png', title: 'Intro to SvelteKit: A Beginner’s Guide', description: 'This is a beginner friendly guide that covers all the basics of SvelteKit', link: '/blog-intro-to-sveltekit', datePublished: 'Sept 17th 2021'},
        {type: 'video', src: '/sveltekit-itunes.png', title: 'Intro to SvelteKit: Build an iTunes Search App!', description: 'Learn how to build an iTunes search app using SvelteKit! This is a beginner friendly tutorial that covers all the basics!', link: 'https://youtu.be/uC6y59y4V4w', datePublished: 'Sept 15th 2021'},
        {type: 'video', src: '/svelteVsVue.png', title: 'Svelte vs Vue: A Svelte crash course and analysis', description: 'A quick but complete look at how to use Svelte and how it compares to Vue! I  build a simple game app with Svelte and do a side-by-side comparison with Vue along the way.', link: 'https://youtu.be/JtQkCbUGPgA', datePublished: 'Aug 31st 2021'},
        {type: 'blog', src: '/vueVsSvelte.jpg', title: 'Svelte vs Vue', description: 'A side-by-side comparison of Vue and Svelte!', link: '/blog-svelte-vs-vue', datePublished: 'Aug 30th 2021'},
        {type: 'video', src: '/petite-vue.jpg', title: 'Building YouTube Search with Petite Vue! (5kb Vue Alternative)', description: 'petite-vue is a new lightweight framework that provides the same template syntax and reactivity mental model with standard Vue. In this tutorial I\'ll explain what petite-vue is, how to use it, and finally create a YouTube search app with it!', link: 'https://youtu.be/Y_g5-7NKp0A', datePublished: 'Aug 15th 2021'},
        {type: 'blog', src: '/petite-vue.webp', title: 'Vue vs petite-vue', description: 'petite-vue is a lightweight Vue alternative that can be “sprinkled” over your project requiring no extra bundling steps or build processes. Let\'s learn how to use it and compare it to standart Vue!', link: '/blog-petite-vue', datePublished: 'Aug 15th 2021'},
      ]
    }
  }
}
</script>

<style lang="css" scoped>
@import url('https://fonts.googleapis.com/css?family=Abril+Fatface|Anton|Marcellus+SC|Shrikhand&display=swap');

.d3 {
  font-weight: 800;
  margin: 0.5em 0;
  color: rgb(30,30,30) ;
  text-transform: uppercase;
  letter-spacing: 0.053em;
  text-shadow: -0.07em 0 1px rgba(255,0,0,0.87), 0.07em 0 1px rgba(0, 255, 255, 0.87);
}
.link:hover {
  color: rgb(30,30,30) ;
  text-shadow: -0.07em 0 1px rgba(255,0,0,0.87), 0.07em 0 1px rgba(0, 255, 255, 0.87);
}
.button:hover {
  box-shadow: -0.15em 0 1px rgba(255,0,0,0.87), 0.15em 0 1px rgba(0, 255, 255, 0.87);
}
.boxShadow {
  box-shadow: -4px 0 rgba(255,0,0,0.87), 2px 2px  rgba(0, 255, 255, 0.87);
}

</style>
