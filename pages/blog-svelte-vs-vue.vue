<template lang="html">
  <div class="body leading-relaxed pt-16 pb-16 md:pb-24 px-6 md:px-0">
    <div class="w-full flex flex-col items-center justify-center border-b mb-8">
      <h1 class="font-bold text-5xl text-center mb-6">Svelte vs Vue</h1>
      <p class="md:w-2/3 pb-16 text-center">A side-by-side comparison of Vue and Svelte!</p>
    </div>
    <div class="w-full p-3 border rounded mb-8">
      Demo Repo: <a href="https://github.com/StephDietz/svelte-game-hub" target="_blank" class="md:ml-4 text-blue-500 underline">https://github.com/StephDietz/svelte-game-hub</a>
    </div>
    <div class="mb-6">
      These days, it seems like a new JavaScript framework pops up every six months, each one claiming to be even more revolutionary than the last. This has created a sort of ‘battle’ of the frameworks, the most popular being Vue, React, and Angular. However, Svelte, an even newer framework, has been gaining popularity and making waves in the web development world.

    </div>
    <div class="mb-6">
      Svelte is known for being faster than most other frontend frameworks due to its novel approach to building user interfaces. In a nutshell, Svelte is not actually a framework, but rather a compiler. Technically speaking, Svelte code is not JavaScript. The compiler takes the Svelte code as an input and uses it to generate the actual JavaScript code, eliminating the need to deploy a library (like we do with other frontend frameworks).

    </div>
    <div class="mb-6">
      I’ve been a loyal Vue developer for the past two years, but hearing about Svelte piqued my interest and got me asking the same thing you’re probably wondering right now: is Svelte the next big thing? Is it even better than Vue and should I be making the switch right now? Well, I’m here to get to the bottom of that and provide you with some answers.

    </div>
    <h2 class="font-bold text-xl mb-6">What is Svelte?</h2>
    <div class="mb-6">
      Similar to Vue, Svelte is a lightweight component-based framework that allows JavaScript developers to write organized, easy-to-read code. However, unlike Vue, it does not utilize the virtual DOM, requires fewer lines of code, and is truly reactive.

    </div>
    <h2 ref="lessCode" class="font-bold mb-6">Less Code</h2>
    <div class="mb-6">
      Every developer wants to achieve their goal with as few lines of code as possible. Less code saves time, reduces bugs, and improves readability. Let’s look at a simple ‘Hello, World!’ example and compare it to Vue.

    </div>
    <CodeCompare class="mb-6" :tabs="codeBlockOne" />
    <div class="mb-6">
      Similar to Vue, Svelte uses templates and single file components, however, you can typically achieve the same result with fewer lines of code due to the lack of boilerplate necessary. In the Svelte example, notice how any variable declared is automatically reactive and can be used in the markup with single curly braces: <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">{text}</span>.

    </div>
    <h2 class="font-bold mb-6">True Reactivity</h2>
    <div class="mb-6">
      According to Rich Harris, the creator of Svelte, “Svelte 3.0 moves reactivity out of the component API and into the language.” So what does this mean? As we’ve already covered, Vue (and most other JavaScript frameworks) relies on an API to tell it when data changed in order to know when to update the Virtual DOM. This means that the reactivity of the framework is tied to a specific API. Without this API, it would be completely unaware when there are changes to the data.

    </div>
    <div class="mb-6">
      Svelte takes a unique approach to this. Rather than running your code top to bottom, it runs it in topological order. The compiler takes all the variables in the Svelte code and creates a dependency graph of who needs who first. In simple terms, if statement A relies on statement B, then statement B will run first regardless of the order in which they are declared. This allows us to then bind variables and achieve true reactivity!

    </div>
    <h2 class="font-bold mb-6">No Virtual DOM</h2>
    <div class="mb-6">
      Today all of the popular frameworks use what is known as the Virtual DOM. The Virtual DOM can be thought of as a copy of the original DOM, which can be easily manipulated and updated without using the DOM APIs. The Virtual DOM can then act as a ‘blueprint’ to make specific changes to the original DOM in a targeted and optimized way. But this does not come without performance penalties. What if we could know how things would change in an app at build time, rather than waiting until run time to do the work?

    </div>
    <div class="mb-6">
      Unlike other frameworks, rather than using the virtual DOM, Svelte takes your components and compiles them into a single vanilla JavaScript bundle that updates the DOM whenever state changes. This means that when your program is running in the DOM, no overhead framework code is injected in the browser, resulting in a faster website. In fact, Svelte is known as the ‘disappearing framework’ because it is not present after the build process.

    </div>
    <h2 class="font-bold text-xl mb-6">Getting started with Svelte</h2>
    <div class="mb-6">
      As previously mentioned, Svelte is a novel type of framework that acts as a compiler, making getting started a little bit confusing at first. Rather than adding it to your app with <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">import</span> or <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">require</span> (as you do with Vue), the easiest way to get started with Svelte is to download or clone the template from <a href="https://github.com/sveltejs/template" target="_blank" class="text-blue-500 underline">https://github.com/sveltejs/template</a>. You can easily do this with the following commands.

    </div>
    <div class="mb-6">
      First, you need to have digit installed globally. To install it run: <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">npm i digit -g</span>
    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      npx degit sveltejs/template svelte-app</br>
      cd svelte-app</br>
      npm install</br>
    </div>
    <div class="mb-6">
      This will download a basic template from Svelte’s GitHub account. We can then start up a development server using the following command:
    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      npm run dev
    </div>
    <div class="mb-6">
      This will serve your app on localhost and rebuild it with <a href="https://rollupjs.org/guide/en/" target="_blank" class="text-blue-500 underline">Rollup</a> every time you make a change.

    </div>
    <h2 class="font-bold text-xl mb-6">Svelte Basics</h2>
    <h2 class="font-bold mb-6">Reactive Variables</h2>
    <div class="mb-6">
      First, let’s talk about how to create reactive variables with Svelte. Unlike Vue, this is done without any special API functions. Simply define them as you would for regular JavaScript variables.

    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      <span>&lt;script&gt;</span></br>
      <span class="ml-4">let userName = ‘Steph Dietz’;</span></br>
      <span class="ml-4">let userAge = 25;</span></br>
      <span class="ml-4">const clearName = () => {</span></br>
      <span class="ml-8">userName = ‘’;</span></br>
      <span class="ml-4">};</span></br>
      <span>&lt;script&gt;</span></br>
    </div>
    <div class="mb-6">
      While <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userName</span> may look like a primitive JavaScript variable, it actually behaves more like an observable. So whenever you reassign the variable, the component will get re-rendered. In the above example, calling <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">clearName</span> will reassign <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userName</span>, which will cause the component to be re-rendered.

    </div>
    <h2 class="font-bold mb-6">Computed Values</h2>
    <div class="mb-6">
      In frontend development we frequently need to create state that is dependent on other variables, and automatically updates when these variables change. For this situation, Svelte has reactive declarations, which looks like this:

    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      $: userInfo = userName + 'is' + userAge + ‘years old.’;

    </div>
    <div class="mb-6">
      In this example we define <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userInfo</span>, which is dependent on two other values, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userName</span> and <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userAge</span>. In order to do this, we use a signature element in the Svelte syntax, the dollar sign, which tells Svelte to re-run this code anytime a referenced value changes. So in the above example, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userInfo</span> will update anytime <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userName</span> or <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userAge</span> changes. ​​Without using the dollar sign, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userInfo</span> will not be updated after the initialization. This is very similar to Vue’s computed properties. Let’s look at a side-by-side comparison of the two.

    </div>
    <CodeCompare class="mb-6" :tabs="codeBlockTwo" />
    <div class="mb-6">
      The most noticeable difference is that Svelte uses fewer lines of code to achieve the same result, <a @click="scrollMeTo('lessCode')" class="text-blue-500 underline">as we’ve already covered</a>.  Another important difference is that Vue requires you to use the keyword <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">this</span>, which is necessary in order to access all of your data in the Vue instance. With Svelte, we already have access to all state defined in the component.

    </div>
    <h2 class="font-bold mb-6">Element Directives</h2>
    <div class="mb-6">
      Svelte’s template syntax is extremely similar to that of Vue’s and has many similar element directives. Let’s compare how we would respond to input events and click events for each.

    </div>
    <CodeCompare class="mb-6" :tabs="codeBlockThree" />
    <div class="mb-6">
      Take a look at the inputs in the example above. In each case, we want to bind the value of the input with the value of <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userName</span> and <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userAge</span>, respectively. Thankfully, both Vue and Svelte have a way of expressing the binding rather than responding to the input event ourselves. Vue uses the <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">v-model</span> directive while Svelte uses <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">bind:value</span>. Using these directives binds the input value to the specified data value. So in our example, as the value in the first input changes, so does <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userName</span>. As a user types in either input, the computed property <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userInfo</span> will be updated, and the component will be re-rendered, displaying the updated value in our HTML.

    </div>
    <div class="mb-6">
      Another important directive available for both Vue and Svelte is the <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">on:</span> directive. In the above Svelte example, we use <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">on:click</span> to call the <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">clearName</span> function, which updates our <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">userName</span> to an empty string. With Vue, we are able to replace <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">on:</span> with its shorthand <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">@</span>. When it comes to element directives, the difference between Vue and Svelte is minimal.

    </div>
    <h2 class="font-bold mb-6">List Rendering</h2>
    <div class="mb-6">
      The need to display list items is an extremely common occurrence in front-end applications. Vue has a core directive, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">v-for</span>, which makes rendering lists of items onto the browser extremely simple. Svelte has a similar way of iterating over lists of values using an each block, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">{#each … }</span>. Here is an example of how it is used.

    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      {#each expression as name}...{/each}

    </div>
    <div class="mb-6">
      You can use each blocks to iterate over any array or array-like value (i.e. any object with a length property). An each block can also have an <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">{:else}</span> clause, which is rendered if the list is empty.

    </div>
    <CodeCompare class="mb-6" :tabs="codeBlockFour" />
    <div class="mb-6">
      As you can see, list rendering is extremely similar between Svelte and Vue. The most important difference to point out is that in Vue, you define your alias for the array element before the source data array, while the opposite is true for Svelte. Also, Svelte requires an end tag, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">{/each}</span>, while Vue does not.

    </div>
    <h2 class="font-bold mb-6">Components</h2>
    <div class="mb-6">
      Components are reusable instances that we can use as custom elements inside our HTML. This allows us to reuse code rather than constantly repeating the same few lines. Part of what makes Vue such a  powerful framework is the simplicity when creating and using components.These components can store all the needed code (HTML, CSS, and JavaScript) in a single file. What makes these components even more powerful is that they are dynamic. You can easily pass data in using the custom <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">prop</span> attribute and emit data using <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">$emit</span>. Similarly, Svelte gives us the ability to create single page components and allows us to pass data in and out in a slightly different way. Let’s look at how we would create a simple input component using each.
    </div>
    <CodeCompare class="mb-6" :tabs="codeBlockFive" />
    <div class="mb-6">
      As you can see in the above example, we have to import our component for both frameworks, but Svelte does not require you to register it like we do with Vue. After importing, it is automatically available for use in our HTML. Svelte also has a unique way of passing data between components. Rather than using the <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">prop</span> attribute to pass in data, we expose the variable to our parent component using  <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">export</span>:

    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      <span>&lt;script&gt;</span></br>
      <span class="ml-4">export let title;</span></br>
      <span>&lt;script&gt;</span></br>
    </div>
    <div class="mb-6">
      We are then able to pass a value from our parent component to our child like this:

    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      <span>&lt;component title=”My Title”&gt;</span></br>
    </div>
    <div class="mb-6">
      Here, we can pass in a static string, or we can use single curly braces to pass in another variable available in our parent component. This gives us one way binding: our parent component can pass data to our child component, but what if we want two way binding? We can do this using <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">bind:value</span>. We still expose our value from the child component, and in our parent component we say:

    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      <span>&lt;script&gt;</span></br>
      <span class="ml-4">let parentTitle = "New Title";</span></br>
      <span>&lt;script&gt;</span></br>
      <span class="">&lt;component bind:title={parentTitle} /&gt;</span></br>

    </div>
    <div class="mb-6">
      Here, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">title</span> is the name of the value exported in our child component and we are using <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">bind:</span> to bind it to <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">parentTitle</span> in our parent component. Now, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">title</span> and <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">parentTitle</span> will always be the same value. This means if you update <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">title</span> in the child component, <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">parentTitle</span> in the parent component will be updated as well, and vice versa.

    </div>
    <div class="mb-6">
      Lastly, let's go over how to communicate click events from the child component to the parent. We can do this by encapsulating the parent's state brackets and passing it down to the child component that triggers it when needed. Let’s set up our child component like this:

    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      <span>&lt;script&gt;</span></br>
      <span class="ml-4">export let submit = () => {}</span></br>
      <span>&lt;script&gt;</span></br>
      <span class="">&lt;button on:click={submit}&gt; Submit&lt;/button&gt;</span></br>

    </div>
    <div class="mb-6">
      Here we are exposing our <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">submit</span> function from the component. This means that we can pass a property <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">submit</span> to the component from our parent that has the desired functionality. If we add this to our parent component:

    </div>
    <div class="whitespace-nowrap overflow-auto flex-none overflow-x-scroll p-1 rounded-md bg-gray-100 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-6">
      <span>&lt;script&gt;</span></br>
      <span class="ml-4">let submitted = false;</span></br>
      <span class="ml-4">let submitFromParent = () => {</span></br>
      <span class="ml-8">submitted = true</span></br>
      <span class="ml-4">}</span></br>
      <span>&lt;script&gt;</span></br>
      <span class="">&lt;component submit={submitFromParent} /&gt;</span></br>

    </div>
    <div class="mb-6">
      Then when we click the button in our child component, our <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">submitFromParent</span> method will run and update the value of <span class="p-1 rounded-md bg-gray-200 font-mono text-sm">submitted</span>.

    </div>
    <h2 class="font-bold text-xl mb-6">Learning Curve</h2>
    <div class="mb-6">
      When writing Svelte code, it feels like writing normal JavaScript and the template syntax is extremely similar to Vue, making the learning curve almost non-existent. I think any experienced JavaScript developer will have no issue learning Svelte as it is very intuitive. The Svelte documentation is detailed and expansive, providing all the necessary information. In addition, there is already a lot of other content providing additional examples, tutorials and discussions. I was able to pick up Svelte in less than a day, and I am confident most developers will be able to do the same.

    </div>
    <h2 class="font-bold text-xl mb-6">Cons</h2>
    <div class="mb-6">
      So far Svelte seems equal or superior to Vue in many ways, but it does have its drawbacks. As I already mentioned, Svelte is not technically JavaScript, which may be a problem in certain unique situations. Svelte is a DSL (domain specific language) that looks like JavaScript, and it has to be compiled to be useful. Why does that matter? If it works in its own way, why should we care that it isn’t JavaScript? Well, most of the time we probably won’t, but there are edge cases. For example, if you were expected to develop a JavaScript app using only a code editor and a browser, you wouldn’t be able to use Svelte at all because you have to install a compiler before you can develop Svelte. In contrast, you can still use runtime-based frameworks like Vue.

    </div>
    <div class="mb-6">
      While the above issue is not likely to occur in practice, one thing that makes Vue a more attractive option to developers is its abundance of community support, tools, and Vue specific libraries. The lack of community may negatively impact your development as you may not have access to specific libraries and plugins that are available for Vue. However, Svelte is still pretty new and is quickly gaining popularity, so this will likely not be an issue in the near future.

    </div>
    <h2 class="font-bold text-xl mb-6">Conclusion</h2>
    <div class="mb-6">
      I think Svelte is one of the better things to happen to front-end development in a while. The concept behind Svelte and its execution enables us to do more, while shipping less. I think we will not only see a lot of developers switch to Svelte in the future, but I also think Vue and other popular frameworks will start adapting some of Sveltes concepts. So should you make the switch today? It depends. If you will need to add developers to your team in the near future, probably not, as Svelte developers may be more difficult to come across. Also if you are building a complex app that will require specific libraries/ plugins, Svelte may not be the best option as of right now. If you don’t fall into either of those categories then I think now is the perfect time to make the switch! I see Svelte becoming one of the leading frameworks within the next couple of years, so get a head start!

    </div>

  </div>
</template>

<script>
import CodeCompare from '/components/CodeCompare.vue';

export default {
  components: {
    CodeCompare
  },
  data() {
    return {
      codeBlockOne: [
        {
          name: 'Svelte',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4">export default {</span></br>
                <span class="ml-8">data() {</span></br>
                <span class="ml-12">return {</span></br>
                <span class="ml-16">text: 'World'</span></br>
                <span class="ml-12"}</span></br>
                <span class="ml-8">}</span></br>
                <span class="ml-4">}</span></br>
                <span>}</span></br>
                <span class="">&lt;/script&gt;</span></br>
                <span>&lt;div&gt;</span></br>
                <span class="ml-4">&lt;h1&gt; Hello, {{ text }}! &lt;/h1&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>`
        },
        {
          name: 'Vue',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4">let text = 'World'</span></br>
                <span class="">&lt;/script&gt;</span></br>
                <span>&lt;div&gt;</span></br>
                <span class="ml-4">&lt;h1&gt; Hello, { text }! &lt;/h1&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>`
        }
      ],
      codeBlockTwo: [
        {
          name: 'Svelte',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4"></span>let userName = 'Steph Dietz';</br>
                <span class="ml-4"></span>let userAge = 25;</br>
                <span class="ml-4"></span>$: userInfo = userName + 'is' + userAge + 'years old.';</br>
                <span class="">&lt;/script&gt;</span></br>`
        },
        {
          name: 'Vue',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4">export default {</span></br>
                <span class="ml-8">data() {</span></br>
                <span class="ml-12">return {</span></br>
                <span class="ml-16">userName: 'Steph Dietz',</span></br>
                <span class="ml-16">userAge: 25</span></br>
                <span class="ml-12"}</span></br>
                <span class="ml-8">},</span></br>
                <span class="ml-8">computed: {</span></br>
                <span class="ml-12">userInfo() {</span></br>
                <span class="ml-16">return this.userName + 'is' + this.userAge + 'years old.';</span></br>
                <span class="ml-12">}</span></br>
                <span class="ml-8">}</span></br>
                <span class="ml-4">}</span></br>
                <span class="">&lt;/script&gt;</span></br>`
        }
      ],
      codeBlockThree: [
        {
          name: 'Svelte',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4"></span>let userName = 'Steph Dietz';</br>
                <span class="ml-4"></span>let userAge = 25;</br>
                <span class="ml-4"></span>$: userInfo = userName + 'is' + userAge + 'years old.';</br>
                <span class="ml-4"></span>const clearName = () => {</br>
                <span class="ml-8"></span>userName = '';</br>
                <span class="ml-4"></span>};</br>
                <span class="">&lt;/script&gt;</span></br>
                <span class="mt-8">&lt;div&gt;</span></br>
                <span class="ml-4">&lt;input bind:value={userName} type="text" /&gt;</span></br>
                <span class="ml-4">&lt;input bind:value={userAge} type="number" /&gt;</span></br>
                <span class="ml-4">&lt;button on:click={clearName}&gt; Clear Name &lt;/button&gt;</span></br>
                <span class="ml-4">&lt;div&gt; {userInfo} &lt;/div&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>

                `
        },
        {
          name: 'Vue',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4">export default {</span></br>
                <span class="ml-8">data() {</span></br>
                <span class="ml-12">return {</span></br>
                <span class="ml-16">userName: 'Steph Dietz',</span></br>
                <span class="ml-16">userAge: 25</span></br>
                <span class="ml-12"}</span></br>
                <span class="ml-8">},</span></br>
                <span class="ml-8">computed: {</span></br>
                <span class="ml-12">userInfo() {</span></br>
                <span class="ml-16">return this.userName + 'is' + this.userAge + 'years old.';</span></br>
                <span class="ml-12">}</span></br>
                <span class="ml-8">}</span></br>
                <span class="ml-8">methods: {</span></br>
                <span class="ml-12">clearName() {</span></br>
                <span class="ml-16">this.userName = '';</span></br>
                <span class="ml-12">}</span></br>
                <span class="ml-8">}</span></br>
                <span class="ml-4">}</span></br>
                <span class="">&lt;/script&gt;</span></br>
                <span class="mt-8">&lt;div&gt;</span></br>
                <span class="ml-4">&lt;input bind:value={userName} type="text" /&gt;</span></br>
                <span class="ml-4">&lt;input bind:value={userAge} type="number" /&gt;</span></br>
                <span class="ml-4">&lt;button on:click={clearName}&gt; Clear Name &lt;/button&gt;</span></br>
                <span class="ml-4">&lt;div&gt; {userInfo} &lt;/div&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>`
        }
      ],
      codeBlockFour: [
        {
          name: 'Svelte',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4"></span>let users = [</br>
                <span class="ml-8">{name: 'Steph', age: 25},</span></br>
                <span class="ml-8">{name: 'Rob', age: 27},</span></br>
                <span class="ml-8">{name: 'Mike', age: 28}</span></br>
                <span class="ml-4">];</span></br>
                <span class="">&lt;/script&gt;</span></br>
                <span class="mt-8">&lt;div&gt;</span></br>
                <span class="ml-4">{#each users as user}</span></br>
                <span class="ml-8">&lt;div&gt;</span></br>
                <span class="ml-12">&lt;p&gt; {user.name} is {user.age} years old. &lt;/p&gt;</span></br>
                <span class="ml-8">&lt;/div&gt;</span></br>
                <span class="ml-4">{/each}</span></br>
                <span class="">&lt;/div&gt;</span></br>

                `
        },
        {
          name: 'Vue',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4">export default {</span></br>
                <span class="ml-8">data() {</span></br>
                <span class="ml-12">return {</span></br>
                  <span class="ml-16"></span>let users = [</br>
                  <span class="ml-20">{name: 'Steph', age: 25},</span></br>
                  <span class="ml-20">{name: 'Rob', age: 27},</span></br>
                  <span class="ml-20">{name: 'Mike', age: 28}</span></br>
                  <span class="ml-16">]</span></br>
                <span class="ml-12"}</span></br>
                <span class="ml-8">}</span></br>
                <span class="ml-4">}</span></br>
                <span class="">&lt;/script&gt;</span></br>
                <span class="ml-4">&lt;div v-for="user in users"&gt;</span></br>
                <span class="ml-8">&lt;p&gt; {user.name} is {user.age} years old. &lt;/p&gt;</span></br>
                <span class="ml-4">&lt;/div&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>`
        }
      ],
      codeBlockFive: [
        {
          name: 'App.svelte',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4"></span>import TopNav from './TopNav.svelte';</br>
                <span class="ml-4"></span>let title = "Enter your name below.";</br>
                <span class="ml-4"></span>let name;</br>
                <span class="ml-4"></span>const submitForm = () => {</br>
                <span class="ml-8"></span>console.log('Submitted!')</br>
                <span class="ml-4"></span>};</br>
                <span class="">&lt;/script&gt;</span></br>
                <span class="">&lt;div&gt;</span></br>
                <span class="ml-8">&lt;h1&gt; Hello, {name} &lt;/h1&gt;</span></br>
                <span class="ml-8">&lt;TopNav title={title} submit={submitForm} bind:name={name} /&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>`

        },
        {
          name: 'Component.svelte',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4"></span>export let title;</br>
                <span class="ml-4"></span>export let name;</br>
                <span class="ml-4"></span>export let submit = () => {};</br>
                <span class="">&lt;/script&gt;</span></br>
                <span class="">&lt;div&gt;</span></br>
                <span class="ml-8">&lt;h1&gt; {title} &lt;/h1&gt;</span></br>
                <span class="ml-8">&lt;input bind:value={name} type="text" /&gt;</span></br>
                <span class="ml-8">&lt;button on:click={submit}&gt; Submit &lt;/button&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>`
        },
        {
          name: 'App.vue',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4"></span>import TopNav from './TopNav.svelte';</br>
                <span class="ml-4">export default {</span></br>
                <span class="ml-8">data() {</span></br>
                <span class="ml-12">return {</span></br>
                <span class="ml-16">title: 'Enter your name below.',</span></br>
                <span class="ml-16">name: ''</span></br>
                <span class="ml-12"}</span></br>
                <span class="ml-8">},</span></br>
                <span class="ml-8">methods: {</span></br>
                <span class="ml-12">submitForm() {</span></br>
                <span class="ml-16">console.log('Submitted!');</span></br>
                <span class="ml-12">}</span></br>
                <span class="ml-8">}</span></br>
                <span class="ml-4">}</span></br>
                <span class="">&lt;/script&gt;</span></br>
                <span class="">&lt;div&gt;</span></br>
                <span class="ml-8">&lt;h1&gt; Hello, {name} &lt;/h1&gt;</span></br>
                <span class="ml-8">&lt;TopNav :title="title" @submit="submitForm()" v-model="name" /&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>`
        },
        {
          name: 'Component.vue',
          code: `<span>&lt;script&gt;</span></br>
                <span class="ml-4">export default {</span></br>
                <span class="ml-8">props: ['title', 'bame']</span></br>
                <span class="ml-4">}</span></br>
                <span class="">&lt;/script&gt;</span></br>
                <span class="">&lt;div&gt;</span></br>
                <span class="ml-8">&lt;h1&gt; {title} &lt;/h1&gt;</span></br>
                <span class="ml-8">&lt;input </span></br>
                  <span class="ml-12">v-bind:value="name"</span> </br>
                  <span class="ml-12">v-on:input="$emit('updateName', $event.target.value)" type="text" /&gt;</span></br>
                <span class="ml-8">&lt;button @click="$emit('submit')"&gt; Submit &lt;/button&gt;</span></br>
                <span class="">&lt;/div&gt;</span></br>`
        }
      ],
    }
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
</style>
