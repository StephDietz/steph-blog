<template lang="html">
  <div class="body leading-relaxed pt-16 pb-16 md:pb-24 px-6 md:px-0">
    <div class="w-full flex flex-col items-center justify-center border-b mb-8">
      <h1 class="font-bold text-5xl text-center mb-6">How much JavaScript do you need to know before learning Svelte?</h1>
      <p class="md:w-2/3 pb-16 text-center">In this tutorial we will take a deep dive into all the JavaScript basics you should know before learning the Svelte framework while building a photo gallery.</p>
    </div>
    <div class="w-full p-3 border rounded mb-8">
      Demo Repo: <a href="https://github.com/StephDietz/javascript-basics" target="_blank" class="md:ml-4 text-blue-500 underline">https://github.com/StephDietz/javascript-basics</a>
    </div>
    <div class="mb-6">
      Many beginners want to jump straight into learning a JavaScript framework without first learning the JavaScript fundamentals. Is this possible? Totally! I am a self-taught JavaScript developer, and this is exactly what I did. Rather than learning the JavaScript basics, I jumped straight into learning the Vue.js framework, so I was learning the framework and JavaScript simultaneously. However this caused some major confusion for me in the long run. Learning JavaScript and a framework simultaneously makes it difficult to identify what is part of the framework and what is actual JavaScript. As I began learning more advanced concepts, I had a hard time understanding vanilla JavaScript examples that did not utilize the Vue framework. As a result, I had to take a step back and relearn the basics without using a framework.

    </div>
    <div class="mb-6">
      While it is possible to learn JavaScript and a framework simultaneously, I do not recommend it. It will create confusion for you in the long run, and will ultimately hinder your learning process. However, Svelte is a novel framework that uses no boilerplate code, and has very little Svelte-specific syntax, making it feel extremely similar to vanilla javascript. As a result, I think that beginner JavaScript developers will have an easier time learning JavaScript and Svelte simultaneously than they would with any other framework. Before diving into Svelte, I think it is important to understand the JavaScript basics. The best way to learn is by doing, so let’s build a photo search app that utilizes the JavaScript basics I think you should know before diving into Svelte.

    </div>
    <h1 class="font-bold text-2xl mb-8">Code Structure</h1>
    <div class="mb-6">
      In order to write JavaScript you must first understand its building blocks. Javascript runs on statements in the order in which they are written. A statement is a group of executable language components terminated by a semicolon as seen below:

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-8">
      <span>console.log(‘This runs first’);</span><br>
      <span>console.log(‘This runs second’);</span><br>
    </div>
    <div class="mb-6">
      In this example, we have two <span>console.log</span> statements that will print text in our console. They will always run in the order in which they are written, meaning we will see ‘This runs first’ in our console before ‘This runs second’. It is also important to note that JavaScript is case sensitive. Let’s alter the above example slightly to be the following:
    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-8">
      <span>console.log(‘This runs first’);</span><br>
      <span>Console.log(‘This runs second’);</span><br>
    </div>
    <div class="mb-6">
      In this example, we will never see the second statement because the ‘C’ in Console is uppercase. Instead, you will receive an error telling you that Console is undefined. This can cause a lot of confusion for beginners at first, so it is important to be hyper aware when naming variables as you will find things breaking and not working with simple case errors.

    </div>
    <h1 class="font-bold text-2xl mb-8">Variables</h1>
    <div class="mb-6">
      A variable is a “named storage” for data that can be declared in three ways: <span>var</span>, <span>let</span>, and <span>const</span>.

    </div>
  </div>
</template>

<script>
import CodeCompare from '/components/CodeCompare.vue';

export default {
  components: {
    CodeCompare
  },
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
span {
  padding: 0.25rem;
  border-radius: 0.375rem;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  background-color: #E5E7EB;
  font-size: 0.875rem;
  line-height: 1.25rem;
}
</style>
