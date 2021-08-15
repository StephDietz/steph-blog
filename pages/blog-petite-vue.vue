<template lang="html">
  <div class="body leading-relaxed pt-16 pb-16 md:pb-24 px-6 md:px-0">
    <div class="w-full flex flex-col items-center justify-center border-b mb-8">
      <h1 class="font-bold text-5xl text-center mb-6">Vue vs petite-vue</h1>
      <p class="md:w-2/3 pb-16 text-center">petite-vue is a lightweight Vue alternative that can be “sprinkled” over your project requiring no extra bundling steps or build processes. Let's learn how to use it and compare it to standart Vue!</p>
    </div>
    <div class="w-full p-3 border rounded mb-8">
      Demo Repo: <a href="https://github.com/StephDietz/petite-vue" target="_blank" class="md:ml-4 text-blue-500 underline">https://github.com/StephDietz/petite-vue</a>
    </div>
    <h2 class="font-bold text-xl mb-6">What is Petite-Vue?</h2>
    <div class="mb-4">
      petite-vue is an alternative distribution of Vue specifically built with progressive enhancement in mind. At only 5.8Kb, it is an extremely lightweight alternative to standard Vue that can be sprinkled throughout your project using Vue-compatible template syntax. petite-vue is similar to Vue in many ways. The main difference is that petite-vue does <a @click="scrollMeTo('noBuildStep')" class="text-blue-500 underline">not require a build step</a>, and thus does not need a compiler, decreasing the overall size.

    </div>
    <div class="mb-6">
      In this article I will not only explain what petite-vue does and how it works, but will also cover how to get started with a few use cases and finally compare it to standard Vue.

    </div>
    <h2 class="font-bold text-xl mb-6">Progressive Enhancement</h2>
    <div class="mb-4">
      The benefit of petite-vue is not just its small bundle size, but also its ability to simplify progressive enhancement. To understand petite-vue, we first must understand what progressive enhancement is.
    </div>
    <div class="mb-6">
      Progressive enhancement is a strategy in web development that prioritizes showing important content before worrying about the way in which this content is displayed. Using this method, content presentation is implemented in one or more optional layers, and is activated based on aspects of the browser or internet connection of the user. This allows everyone to access the most important content and functionality of the web app, while users with faster internet or additional browser features can receive the more enhanced version. For example, if a user with a slow network visits a site that relies on a script to display initial content, they will be stuck with a blank screen until the script loads. Following the principles of progressevie enhancement, the core content in this case should be loaded in the HTML rather than relying on scripts which may never load.
    </div>
    <h2 class="font-bold text-xl mb-6">Petite-Vue Unique Features</h2>
    <h3 ref="noBuildStep" class="font-bold mb-6">No build tooling </h3>
    <div class="mb-4">
      While standard Vue can be used with or without a build step, the optimal usage involves a build setup making it better suited when building SPAs or apps with heavy interactions. Using standard Vue without a build step actively opts you out of: the Vue CLI, single file components, and smaller/more optimized bundles. So while a buildless implementation of standard Vue is possible, it provides a less optimal developer experience. petite-vue, on the other hand, requires no extra bundling steps or build processes. Since petite-vue was built to sprinkle interactions throughout a project rather than using heavy interactions, the CLI and SFCs are not necessary. To get started with petite-vue  you simply load it from a CDN:
    </div>
    <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;script src="https://unpkg.com/petite-vue" defer init&gt;&lt;/script&gt;</code>
    <h3 class="font-bold my-6">No virtual DOM</h3>
    <div class="mb-6">
      Unlike Vue and most other frontend frameworks, petite-vue does not use the <a href="https://programmingwithmosh.com/react/react-virtual-dom-explained/" target="_blank" class="text-blue-500 underline">virtual DOM</a>, but rather it mutates the DOM in place. Standard Vue pre-compiles all the templates, eliminating the need for template processing at runtime. As mentioned earlier, standard Vue can be used without a build step, but it is not optimal as it creates a large overhead. By navigating the existing DOM and mutating it directly, petite-vue avoids all this overhead. In other words, the DOM is the template, making petite-vue much more efficient in progressive enhancement scenarios.
    </div>
    <h3 class="font-bold my-6">Vue compatible template syntax</h3>
    <div class="mb-6">
      It is extremely simple for Vue developers to move between petite-vue and standard Vue due to the compatible template syntax. petite-vue uses most of the familiar syntax of Vue. Not only does this familiar syntax make petite-vue easy to learn, but also easy to transition between the two
    </div>
    <h2 class="font-bold text-xl mb-6">Usage</h2>
    <div class="mb-4">
      So now let's go over how to use petite-vue in a project! First, we have to add it to our project. We can do this by loading it from a CDN:
    </div>
    <code class="p-1 rounded-md bg-gray-200 font-mono text-sm">&lt;script src="https://unpkg.com/petite-vue" defer init&gt;&lt;/script&gt;</code>
    <div class="my-4">
      In the above line of code, the <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">defer</span> attribute makes the script execute after HTML content is parsed, while the <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">init</span> attribute tells petite-vue to automatically query and initialize all elements that are using petite-vue on the page. How do we communicate which elements are using petite-vue? Great question! We simply add v-scope to the element. Let’s look at an example.
    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      &lt;script src="https://unpkg.com/petite-vue" defer init&gt;&lt;/script&gt;</br>
      &lt;!-- anywhere on the page --&gt;</br>
      &lt;div v-scope="{ count: 0 }"&gt;</br>
      <span class="ml-6">{ count }</span></br>
      <span class="ml-6">&lt;button @click="count++"&gt;inc&lt;/button&gt;</span></br>
      &lt;/div&gt;</br>
    </div>
    <div class="mb-4">
      Here we added <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">v-scope</span> to identify a region on the page that will be controlled by petite-vue. The <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">v-scope</span> directive is also used to pass in states that a particular element will have access to. In the above example, we pass in <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">count</span>, and can use the familiar Vue syntax to add one to <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">count</span> every time the button is clicked.
    </div>
    <div class="mb-4">
      Alternatively, if you don’t want to auto <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">init</span>, remove the <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">init</span> attribute and move the scripts to the end of  <code>&lt;body&gt;</code>, we can use the ES module build. ES modules are javascript files using <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">import</span> and <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">export</span> statements that are loaded using scripts with <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">type=”module”</span>. In contrast to classic scripts, variables declared inside modules are scoped to the file itself. Using this method, we will import the <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">createApp</span> function from petite-vue, which accepts a data object that serves as the root scope for all expressions. To create the same counter button as before using this method, the code would look like this:
    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      <span>&lt;script type="module"&gt;</span></br>
      <span>import { createApp } from 'https://unpkg.com/petite-vue?module'</span></br>
      <span>createApp({</span></br>
      <span class="ml-8">{ count }</span></br>
      <span class="ml-8">count: 0,</span></br>
      <span class="ml-8"increment() {</span></br>
      <span class="ml-10">this.count++</span><br>
      <span class="ml-8">}</span></br>
      <span>}).mount()</span></br>
      <span class="pb-6">&lt;/script&gt;</span></br>
      <span >&lt;!-- v-scope value can be omitted --&gt;</span></br>
      <span class="ml-6">&lt;div v-scope="{ count: 0 }"&gt;</span></br>
      <span class="ml-10">{ count }</span></br>
      <span class="ml-6">&lt;/div&gt;</span></br>
      <span class="ml-6">&lt;button @click="increment"&gt;inc&lt;/button&gt;</span></br>
      <span>&lt;/div&gt;</span></br>
    </div>
    <div class="my-4">
      Notice that <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">v-scope</span> does not need to have a value here, and simply directs petite-vue to process the element.

    </div>
    <div class="mb-4">
      We’ve already touched on <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">v-scope</span>, but there is another petite-vue exclusive feature worth mentioning, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">v-effect</span>. This directive is used to execute inline reactive statements.

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      &lt;div v-scope="{ count: 0 }"&gt;</br>
      <span class="ml-6">&lt;div v-effect="$el.textContent = count"&gt;&lt;/div&gt;</span></br>
      <span class="ml-6">&lt;button @click="count++"&gt;++&lt;/button&gt;</span></br>
      &lt;/div&gt;
    </div>
    <div class="my-4">
      In the above example, the effect uses  <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">count</span> which is a reactive data source, so it will re-run whenever  <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">count</span> changes.

    </div>
    <div class="mb-6">
      Now we are familiar with how petite-vue works, as well as it’s new features unfamiliar to standard Vue. While petite-vue supports many familiar features of Vue, due to its small scope, not all are supported. Let’s take a look at the Vue features that remain, as well as those that <a href="https://github.com/vuejs/petite-vue" target="_blank" class="text-blue-500 underline">have been dropped</a>.

    </div>
    <h2 class="font-bold text-xl mb-6">Supported:</h2>
    <div class=" ml-12">
      <ul class="list-disc">
        <li>text bindings</li>
        <li>v-bind and : : class and style special handling</li>
        <li>v-on and @ : event handling</li>
        <li>v-model: represents all inputs types and non-string :value bindings</li>
        <li>v-if / v-else  / v-else-if</li>
        <li>v-for</li>
        <li>v-show</li>
        <li>v-hmtl</li>
        <li>v-pre</li>
        <li>v-once</li>
        <li>v-cloak</li>
        <li>reactive()</li>
        <li>nextTick()</li>
        <li>Template refs</li>
      </ul>
    </div>
    <h2 class="font-bold text-xl my-6">Not Supported:</h2>
    <div class=" ml-12">
      <ul class="list-disc">
        <li>ref() and computed()</li>
        <li>Render functions:petite-vue has no virtual DOM</li>
        <li>Reactivity for collection types: Map, Set, etc.</li>
        <li>Transition, keep-alive, &lt;teleport&gt;, and &lt;suspense&gt; components</li>
        <li>v-for: deep destructure</li>
        <li>v-on="object"</li>
        <li>v-is and &lt;component :is="newComponent&gt;></li>
        <li>v-bind:style auto-prefixing</li>

      </ul>
    </div>
    <h2 class="font-bold text-xl my-6">Compare to Vue </h2>
    <div class="mb-6">
      Overall, I enjoyed using petite-vue, and found it extremely simple to pick up due to its familiar Vue syntax. While it is not a replacement for Vue, it is a great option for adding small interactivity/reactivity to existing projects or projects that should be kept simple in scope. I had no issue using petite-vue to make my vision come to life, and was able to do so in a couple of hours, making me confident that this is something I’ll be using more in the future. One use case that I’m interested in testing next is using petite-vue to create prototypes, making the prototype more similar to the target framework of the final product, thus making it simple to upgrade to standard Vue when needed.
    </div>
    <h2 class="font-bold text-xl my-6">Conclusion</h2>
    <div class="mb-4">
      Overall, petite-vue is great for adding minimal interactions throughout a project that you want to keep somewhat simple in scope. It provides a great method of enhancing your otherwise normal HTML with little effort and few lines of code. petite-vue has great potential for simple projects that only require minimal interactions such as prototyping, adding Vue functionality to existing projects, or building static landing pages. With its Vue compatible syntax, it will be extremely comfortable for Vue developers to learn and use.
    </div>
    <div class="mb-6">
      petite-vue has a lot of potential, but it is still new. While it is already a functional and useful tool, its docs include a disclaimer warning that it will most likely be buggy and may still have some API changes. The next time I come across a project that would benefit from petite-vue, I’ll definitely be using it again, but use at your own risk!
    </div>
    <div class="mt-8 border-t py-8">
      <p class="font-bold mb-2">Written By</p>
      <div class="flex items-center">
        <div class="h-10 w-10 rounded-full bg-cover bg-center mr-4" style="background-image: url(/profile.jpg)"></div>
        <p>Stephanie Dietz</p>
      </div>
    </div>
    <div class="pt-8 border-t text-sm text-gray-500">
      Last Edited on Aug 15th 2021
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    scrollMeTo(refName) {
      var element = this.$refs[refName];
      var top = element.offsetTop;

      window.scrollTo(0, top);
    }
  }
}
</script>

<style lang="css" scoped>
.body {
  max-width: 800px;
  margin: 0 auto;
}
</style>
