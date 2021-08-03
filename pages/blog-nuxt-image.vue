<template lang="html">
  <div class="leading-relaxed px-12 md:px-40 lg:px-60 mt-16 md:mt-24 pb-16 md:pb-24">
    <div class="w-full flex flex-col items-center justify-center border-b mb-8">
      <h1 class="font-bold text-5xl text-center mb-6">Optimize your images with Nuxt Image</h1>
      <p class="md:w-2/3 pb-16 md:pb-24 text-center">Nuxt image handles the hard parts of optimizing assets through an intuitive interface. Let's learn how to use it!</p>
    </div>
    <div class="w-full p-3 border rounded mb-8">
      Demo Repo: <a href="https://github.com/StephDietz/nuxt-img" target="_blank" class="md:ml-4 text-blue-500 underline">https://github.com/StephDietz/nuxt-img</a>
    </div>
    <div class="mb-6">
      Now more than ever, online experiences are supplementing in-person experiences. Most people would not hesitate to make an online purchase, but they expect to see a high quality image of the product they intend to buy. These images often come in obscure formats and high resolution files designed to preserve the image quality. However, speed and quality are often at odds in the web development process. Slow load times and blurry visuals are equally detrimental, creating a common problem for developers to solve: How can we optimize images in a way that delivers the highest quality image in the right format, dimension, and resolution, while keeping the smallest possible size?
    </div>
    <div class="mb-6">
      While workflows and techniques exist to aid developers in managing images in the modern web, it is far from trivial. We need an intuitive way to optimize assets without adding significant overhead to the development workflow.
    </div>
    <h2 class="font-bold text-xl mb-6">What is Nuxt?</h2>
    <div class="mb-6">
      Nuxt is a frontend framework built on top of Vue. Why use Nuxt over Vue? Nuxt offers many features that would be complex to achieve with plain Vue, including: server-side rendering tot improve SEO, automatically generated routes, and automatic code splitting with pre-rendered pages, just to name a few. Nuxt is a powerful framework that makes developing apps easier.  If your project requires these features, Nuxt will be an excellent choice.
    </div>
    <h2 class="font-bold text-xl mb-6">Nuxt Image</h2>
    <div class="mb-6">
      Nuxt Image is a plug-and-play image optimization module for Nuxt apps. It handles the difficult parts of image optimization, providing an intuitive interface for transforming and optimizing assets. The image module comes with two components: nuxt-img and nuxt-picture, which are drop-in replacements for their native counterparts, <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;img&gt;</code> and <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;picture&gt;</code>. One advantage of these components is they don’t output any unexpected markup while serving your images.
    </div>
    <h2 class="font-bold text-xl mb-6">The Problem</h2>
    <div class="mb-6">
      Users and companies alike prefer faster sites. In fact, if a page takes longer than three seconds to load, the site will likely be abandoned. And, since people like faster loading pages, Google does as well. One of the main culprits of a slow-loading website are non-optimized images. By optimizing our images we will not only increase and maintain traffic, but will also get better search engine rankings.
    </div>
    <div class="mb-6">
      Let’s say we are given an image to display straight from the photographer unoptimized. For example, 5mb in size and 4,000 x 6,000 pixels. Untouched, this image would have a dramatic impact on the speed of our site, as it exceeds our needs greatly. Let’s assume the maximum size we need the image to be is 2,000px, however we want to optimize the image at the standard breakpoints for smaller devices (i.e., 320px, 640px, 768px, 1024px). To achieve this, we would have to generate five different images as well as write the html with all the responsive breakpoints properly defined. All of this for one picture! Not thanks. Nuxt Image will simplify this process and save us time.
    </div>
    <h2 class="font-bold text-xl mb-6">The Solution</h2>
    <div class="mb-6">
      With Nuxt image, all we need to do is add our image using the nuxt-image component. <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;nuxt-img&gt;</code> outputs a native <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;img&gt;</code> tag directly and can be used just like we would use a normal <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;img&gt;</code> tag. To optimize our image in the above scenario, all we need to do is:
    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      &lt;nuxt-img<br>
        <span class="ml-8">src=”/my-image.png”</span><br>
        <span class="ml-8">alt=”My Image”</span><br>
        <span class="ml-8">sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"/&gt;</span>
    </div>
    <div class="mb-6">
      It’s that easy! When our site is built, Nuxt will generate all of the assets we need, and will configure our <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;img&gt;</code> tag for us with the specified breakpoints. Here is the HTML that will be generated by nuxt-image:
    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      &lt;img<br>
        <span class="ml-8">src=”/_ipx/my-image.png?w=1280”</span><br>
        <span class="ml-8">alt=”My Image”</span><br>
        <span class="ml-8">sizes=”(max-width: 320px) 100vw,</span><br>
        <span class="ml-16">(max-width: 640px) 100vw</span><br>
        <span class="ml-16">(max-width: 768px) 100vw,</span><br>
        <span class="ml-16">(max-width: 1024px) 100vw, 100vw"</span><br>
        <span class="ml-8">srcset=”</span><br>
        <span class="ml-16">/_ipx/my-image.png?w=320 320w,</span><br>
        <span class="ml-16">/_ipx/my-image.png?w=640 640w,</span><br>
        <span class="ml-16">/_ipx/my-image.png?w=768 768w,</span><br>
        <span class="ml-16">/_ipx/my-image.png?w=1024 1024w,</span><br>
        <span class="ml-16">/_ipx/my-image.png?w=2000 2000w”/&gt;</span>
    </div>
    <div class="mb-6">
      If we generate a Lighthouse report for our app using our normal <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;img&gt;</code> tag vs using <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;nuxt-img&gt;</code> we can see how nuxt-image improves our score significantly.
    </div>
    <div class="flex md:flex-row flex-col items-center justify-center">
      <div class="w-full md:w-1/2 md:p-8 mb-4 md:mb-0 flex flex-col items-center justify-center">
        <nuxt-img src="/lightHouseBad.png" alt="lighthouse" class="w-3/4" sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"/>
        <p class="text-center text-xs text-gray-600 mt-2">Lighthouse report for app NOT using Nuxt-Image</p>
      </div>
      <div class="w-full md:w-1/2 md:p-8 mb-4 md:mb-0 flex flex-col items-center justify-center">
        <nuxt-img src="/lightHouseGood.png" alt="lighthouse" class="w-3/4" sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"/>
        <p class="text-center text-xs text-gray-600 mt-2">Lighthouse report for app using Nuxt-Image</p>
      </div>
    </div>
    <div class="mb-6">
      Most noteworthy, we can see that 'properly size images' is no longer listed as an area for improvement when using nuxt-image, as we would expect.
    </div>
    <div class="flex md:flex-row flex-col items-center justify-center mb-6">
      <div class="md:w-1/2 md:p-8 mb-4 md:mb-0 flex flex-col items-center justify-center">
        <nuxt-img src="/lightHouse2Bad.png" alt="lighthouse" class="w-3/4" sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"/>
        <p class="text-center text-xs text-gray-600 mt-2">Lighthouse report for app NOT using Nuxt-Image</p>
      </div>
      <div class="md:w-1/2 md:p-8 mb-4 md:mb-0 flex flex-col items-center justify-center">
        <nuxt-img src="/lightHouse2Good.png" alt="lighthouse" class="w-3/4" sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"/>
        <p class="text-center text-xs text-gray-600 mt-2">Lighthouse report for app using Nuxt-Image</p>
      </div>
    </div>
    <h2 class="font-bold text-xl mb-6">Summing it up</h2>
    <div class="">
      When using images in web development, optimization is key. It will not only maintain visitors by increasing loading times, but will even help get new traffic by improving SEO. Nuxt Image makes the process of optimizing our assets quick and simple without adding any significant overhead, so give it a shot! You can deploy your Nuxt app in a few clicks and zero configuration using Vercel! Here’s a quick tutorial on how to do that: <a href="https://vercel.com/guides/deploying-nuxtjs-with-vercel" target="_blank" class="text-blue-500 underline">https://vercel.com/guides/deploying-nuxtjs-with-vercel</a>
    </div>
    <div class="mt-8 border-t py-8">
      <p class="font-bold mb-2">Written By</p>
      <div class="flex items-center">
        <div class="h-10 w-10 rounded-full bg-cover bg-center mr-4" style="background-image: url(/profile.jpg)"></div>
        <p>Stephanie Dietz</p>
      </div>
    </div>
    <div class="pt-8 border-t text-sm text-gray-500">
      Last Edited on Aug 2nd 2021
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
</style>
