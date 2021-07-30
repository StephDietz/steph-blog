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
        <div class="relative w-48 h-48 mt-10 md:mt-0 overflow-hidden" style="border-radius: 999px;">
          <nuxt-img
            src="/profile.jpg"
            alt="profilePic"
            sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
            class="absolute"/>
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
            <contentCard :item="recent" :index="index" class="w-full"/>
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
        {src: '/vercel.png', title: 'Deploy a Vue, Vite, and Tailwind project to Vercel', description: 'Learn how to set up your Vue, Vite, and Tailwind project and deploy it instantly on Vercel.', link: 'https://vercel.com/guides/vue-vite-tailwind', datePublished: 'July 11th 2021'},
        {src: '/youtube.png', title: 'Set up a new Vue 3 project with Vite and Tailwind (Deploy to Vercel!)', description: 'Learn how to create a new Vue 3 project with Vite, install Tailwind, and deploy our project to Vercel! I’ll take you through every step from start to finish.', link: 'https://www.youtube.com/watch?v=ftT8nHHCZrI&t=2s', datePublished: 'July 20th 2021'},
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
