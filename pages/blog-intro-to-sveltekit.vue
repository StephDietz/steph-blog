<template lang="html">
  <div class="body leading-relaxed pt-16 pb-16 md:pb-24 px-6 md:px-0">
    <div class="w-full flex flex-col items-center justify-center border-b mb-8">
      <h1 class="font-bold text-5xl text-center mb-6">Intro to SvelteKit: A Beginner’s Guide</h1>
      <p class="md:w-2/3 pb-16 text-center">This is a beginner friendly guide that covers all the basics of SvelteKit</p>
    </div>
    <div class="w-full p-3 border rounded mb-8">
      Demo Repo: <a href="https://github.com/StephDietz/sveltekit-itunes-search" target="_blank" class="md:ml-4 text-blue-500 underline">https://github.com/StephDietz/sveltekit-itunes-search</a>
    </div>
    <div class="mb-8">
      Creating Svelte apps just got even better thanks to SvelteKit. This new Svelte framework is intuitive and easy to use, even for beginners. It adds key features to a Svelte app, such as routing, layouts, and server-side rendering. You can think of it as an ambitious Next.js for Svelte! In this tutorial we will look at the main features SvelteKit offers, how to begin building a SvelteKit project, and how it compares to vanilla Svelte.

    </div>
    <h1 class="font-bold text-2xl mb-8">What is Svelte? </h1>
    <div class="mb-8">
      Before we dive into SvelteKit, let’s quickly review what Svelte is. Svelte is a lightweight component-based framework that allows JavaScript developers to write organized, easy-to-read code. Svelte is known for being faster than most other frontend frameworks due to its novel approach to building user interfaces. In a nutshell, Svelte is not actually a framework, but rather a compiler. The compiler takes the Svelte code as an input and uses it to generate the actual vanilla JavaScript code. By compiling your code during the build process into a single vanilla JavaScript file, it eliminates the need to deploy a library (like we do with other frontend frameworks). If you are interested in taking a deeper dive into vanilla Svelte, check out my last <a href="https://steph-dietz.com/blog-svelte-vs-vue" target="_blank" class="text-blue-500 underline">blog post</a>.

    </div>
    <h1 class="font-bold text-2xl mb-8">What is SvelteKit? </h1>
    <div class="mb-8">
      SvelteKit is a lightweight component-based framework that allows JavaScript developers to create both small and large scale web applications with a smaller footprint. SvelteKit does much of the heavy lifting, making it simple to create web apps with all the modern best practices. It provides a lightning-fast development experience by leveraging Vite, which makes updates instant and precise. SvelteKit also uses <span>svelte-preprocess</span> package to provide built-in support for common plugins such as Babel, TypeScript, SASS etc. You can think of SvelteKit as Next.js for Svelte, complete with server-side rendering, routing, code-splitting, and adapters for different serverless platforms. It gives you the functionality you need to create a ready-to-go application, and is beginner friendly.

    </div>
    <h1 class="font-bold text-2xl mb-8">Why use SvelteKit?</h1>
    <div class="mb-8">
      SvelteKit is a modern framework that builds fast, high-performance web applications of all sizes while simultaneously reducing the amount of code used. It takes advantage of all the modern practices, making it an ideal framework.

    </div>
    <h2 class="font-bold mb-8">Server-side Rendering</h2>
    <div class="mb-4">
      Server-side rendering (SSR) allows developers to pre-populate the web app with custom user data directly on the server. With SSR, clients receive a pre-rendered page on demand rather than waiting for specific elements to load. Single page applications, on the other hand, render the web page when the client requests them. SPAs are thus structured as a single HTML page with no preloaded content.

    </div>
    <div class="mb-8">
      SvelteKit supports server-side rendering, meaning it first pre-renders the HTML on the server-side and then sends it to the user’s browser. The browser then takes over the execution. At this point, the web app behaves like an SPA. This increases the performance of the app and drives up SEO.

    </div>
    <h2 ref="adapters" class="font-bold mb-8">Adapters</h2>
    <div class="mb-4">
      Before a SvelteKit app can be deployed, you first need to adapt it for your deployment target. Adapters are small plugins that take the built app as input and generate output for deployment. They are oftentimes optimised for a specific hosting provider, however some adapters, like <span>adapter-static</span>, build output that can be hosted on numerous hosting providers. You can generally find information about deployment in your adapter's documentation.
    </div>
    <div class="mb-4">
      For example, if you wanted to deploy your app to Vercel, you would simply add <span>"@sveltejs/adapter-vercel": "next"</span> to the <span>devDependencies</span> in your <span>package.json</span> and run <span>npm install</span>.
    </div>
    <div class="mb-4">
      Then in your svelte.config.js:

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-8">
      <span>import vercel from '@sveltejs/adapter-vercel';</span><br>
      <span class="">export default {</span><br>
      <span class="ml-4">kit: {</span><br>
      <span class="ml-8">...</span><br>
      <span class="ml-8">adapter: vercel()</span><br>
      <span class="ml-4">}</span><br>
      <span class="">};</span>
    </div>
    <h1 class="font-bold text-2xl mb-8">Getting Started</h1>
    <div class="mb-4">
      First, you can initiate a new SvelteKit project by running the following command in your terminal:

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-4">
      npm init svelte@next svelteKit-app
    </div>
    <div class="mb-4">
      You will be prompted to answer a few questions to customize your project. You will be prompted to answer a few questions. I recommend selecting 'SvelteKit demo app' in response to the first. This will create a SvelteKit development environment with a functioning example project. You can also select ‘Skeleton Project’ for the first question, but the demo app is a good learning tool in project structure, so for your first project I recommend using it.

    </div>
    <div class="mb-4">
      Next you need to move into the project directory to install its dependencies and run the project locally.

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-4">
      cd svelteKit-app<br>
      npm install<br>
      npm run dev -- --open<br>

    </div>
    <div class="mb-4">
      This will open your demo app in the browser. You’ll notice it provides you with default routing, layouts, load functions and components for you to build off of. In your project route you will see some configuration files including your package.json, the static folder, and the src folder. You will mostly be working out of the src folder, which has the following structure.

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-8">
      <span>src</span><br>
      <span>├── app.css</span><br>
      <span>├── app.html</span><br>
      <span>├── global.d.ts</span><br>
      <span>├── hooks.js</span><br>
      <span>├── lib</span><br>
      <span>│<span class="ml-3">├── Counter</span></span><br>
      <span>│<span class="ml-3">│<span class="ml-2">└── index.svelte</span></span></span><br>
      <span>│<span class="ml-3">├── form.js</span></span><br>
      <span>│<span class="ml-3">└── Header</span></span><br>
      <span>│<span class="ml-8">├── index.svelte</span></span><br>
      <span>│<span class="ml-8">└── svelte-logo.svg</span></span><br>
      <span>└── routes</span><br>
      <span><span class="ml-4">├── __layout.svelte</span></span><br>
      <span><span class="ml-4">├── about.svelte</span></span><br>
      <span><span class="ml-4">├── index.svelte</span></span><br>
      <span><span class="ml-4">└── todos</span></span><br>
      <span><span class="ml-10">├── _api.js</span></span><br>
      <span><span class="ml-10">├── index.json.js</span></span><br>
      <span><span class="ml-10">├── index.svelte</span></span><br>
      <span><span class="ml-10">└── [uid].json.js</span></span><br>

    </div>
    <h2 class="font-bold mb-8">Routing</h2>
    <div class="mb-4">
      SvelteKit includes a client-side-router. It is a filesystem-based router that updates the page contents after intercepting navigations. The code structure is defined by the contents of the <span>src/routes</span> directory.

    </div>
    <div class="mb-4">
      Routing in SvelteKit is similar to other SSR frameworks such as Next.js. It uses <span>.svelte</span> filenames inside of the <span>src/routes</span> directory to determine the pages route. For example, if you want to navigate to <span>/home</span> page, then SvelteKit will render a <span>home.svelte</span> file to the <span>src/routes</span> folder. The file <span>src/routes/home.svelte</span> will correspond to <span>/home</span> route. If you want to create nested routes, you need to create a folder for each sub-route. Having an <span>index.svelte</span> file within that folder will create a route for the folder name. This makes the navigation process extremely simple.

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-4">
      <span>src</span><br>
      <span>└── routes</span><br>
      <span><span class="ml-4">├── home.svelte</span></span>-->	localhost:3000/home<br>
      <span><span class="ml-4">└── about</span></span><br>
      <span><span class="ml-10">├── index.svelte</span></span>-->	localhost:3000/about<br>
      <span><span class="ml-10">└── products.svelte</span></span>--> 	localhost:3000/about/products<br>

    </div>
    <div class="mb-4">
      SvelteKit also supports advanced routing such as using dynamic parameters. For example, if you need to include an ID in a route and display data associated with that ID, the route would look as follows:

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-4">
      localhost:3000/user/{id}

    </div>
    <div class="mb-4">
      In order to do this, you must create a folder named <span>user</span> and insert files for the dynamic parameters. In the above example, we would need a file called <span>[id].svelte</span>, where the square bracket indicated the variable inside the dynamic parameter.

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-4">
      <span>src</span><br>
      <span>└── routes</span><br>
      <span><span class="ml-4">└── user</span></span><br>
      <span><span class="ml-10">├── [id].svelte</span></span><br>

    </div>
    <div class="mb-4">
      Now that we have our <span>[id].svelte</span> file, we can access that dynamic parameter from the variable in the package <span>$app/stores</span>. Since the page variable is a store, we need to prefix the variable with <span>$</span> and the dynamic parameter will be under an object called <span>params</span>.

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-8">
      <span>&lt;script&gt;</span><br>
      <span class="ml-4">import {page} from ‘$app/stores’;</span><br>
      <span>&lt;/script&gt;</span><br>
      <span>&lt;p&gt; Display user info from: {$page.params.id} &lt;/p&gt;</span><br>
    </div>
    <h2 class="font-bold mb-8">Layouts</h2>
    <div class="mb-4">
      Pages are not just standalone components. Upon navigation, the existing component will be destroyed, and a new one will take its place, but oftentimes there are elements that should be displayed on every page, such as a header or footer. Instead of adding these to every page file, we can use layout components.

    </div>
    <div class="mb-4">
      Components can be wrapped in a layout component using the <span>&lt;slot&gt;</span> tag, which indicates where the child component should be placed within the parent layout. To create a layout component that applies to every page,name a file <span>src/routes/__layout.svelte</span>. The default layout component simply contains a single <span>&lt;slot&gt;</span> tag, but we can add whatever markup, styles, and behavior we want.  For example, we can add a navbar like this:

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-4">
      <span class="text-gray-400">&lt;!-- src/routes/__layout.svelte --&gt;</span><br>
      <span>&lt;nav&gt;</span><br>
      <span class="ml-4">&lt;a href="/"&gt;Home&lt;/a&gt;</span><br>
      <span class="ml-4">&lt;a href="/about"&gt;About&lt;/a&gt;</span><br>
      <span class="ml-4">&lt;a href="/settings"&gt;Settings&lt;/a&gt;</span><br>
      <span>&lt;/nav&gt;</span><br>

      <span>&lt;slot&gt;&lt;/slot&gt;</span><br>

    </div>
    <div class="mb-4">
      In this example, the nav bar will always be visible. The only thing changing is the content within the slot which will correspond to the <span>/</span> , <span>/about</span>, and <span>/settings</span> pages.
    </div>
    <div class="mb-8">
      SvelteKit also allows us to create nested layouts. Suppose rather than having a single <span>/team</span> page, we have nested pages such as <span>/team/lead</span> and <span>team/creative</span>. We are able to create a layout that only applies to pages below <span>/team</span> while still inheriting the root layout at the top-level. To do this, we create the layout the same way we did before, but name the file <span>src/routes/team/__layout.svelte</span>.

    </div>
    <h2 class="font-bold mb-8">Static Pages and Prerendering</h2>
    <div class="mb-4">
      As I mentioned earlier, SvelteKit builds apps for different environments using <a @click="scrollMeTo('adapters')" class="text-blue-500 underline">adapters</a>. If the app does not rely on any dynamic data, it could consist entirely of static files. There is an <span>adapter-static</span> that can be installed, which turns SvelteKit into a static site generator. This means that it would render the entire app into a collection of static files at build time, which would prevent us from adding pages that depend on server-side rendering.
    </div>
    <div class="mb-4">
      Instead of making all of our pages static, we can use another SvelteKit feature which allows us to prerender individual files. For example, if we have an about page that consists of static content, rendering the page on every request would be unnecessary. Instead, we can prerender the page by adding the following code snippet at the top of the <span>about.svelte</span> file:

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-8">
      <span>&lt;script context="module"&gt;</span><br>
      <span class="ml-4">export const prerender = true;</span><br>
      <span>&lt;/script&gt;</span><br>

    </div>
    <h2 class="font-bold mb-8">Endpoints</h2>
    <div class="mb-4">
      So now we know how to render static pages, but what if we want to fill our page with dynamic content? To do this, we need to fetch our data from an API endpoint. Usually this would come from the backend, but SvelteKit makes it simple to turn your application full stack using endpoint pages. These modules are written in <span>.js</span> (or <span>.ts</span>) and export functions corresponding to HTTP methods. For example, a hypothetical blog page, <span>/blog/article</span>, might request data from <span>/blog/article.json</span>, which could be represented by a <span>src/routes/blog/[slug].json.js</span> endpoint:

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-4">
      <span>import db from '$lib/database';</span><br>
      <span class="text-gray-400">/**</span><br>
      <span class="text-gray-400">* @type {import('@sveltejs/kit').RequestHandler}</span><br>
      <span class="text-gray-400">*/</span><br>
      <span>export async function get({ params }) {</span><br>
      <span class="text-gray-400 ml-4">// the `slug` parameter is available because this file</span><br>
      <span class="text-gray-400 ml-4">// is called [slug].json.js</span><br>
      <span class="ml-4">const { slug } = params;</span><br>
      <span class="ml-4">const article = await db.get(slug);</span><br>
      <span class="ml-4">if (article) {</span><br>
      <span class="ml-8">return {</span><br>
      <span class="ml-12">body: {</span><br>
      <span class="ml-16">article</span><br>
      <span class="ml-12">}</span><br>
      <span class="ml-8">};</span><br>
      <span class="ml-4">}</span><br>
      <span>}</span><br>

    </div>
    <div class="mb-4">
      This function will return a <span>{ status, headers, body }</span> object representing the response, where the status is the <span>HTTP</span> status code. Endpoints also have access to fetch in case you need to request data from external APIs. For endpoints that handle other <span>HTTP</span> methods, like <span>POST</span>, export the corresponding function:

    </div>
    <div class="p-1 rounded-md bg-gray-200 font-mono text-sm w-full p-6 tracking-wide leading-relaxed mb-8">
      export function post(request) {...}
    </div>
    <h2 class="font-bold mb-8">Loading</h2>
    <div class="mb-8">
      Each page or a layout can export a load function which will run before the component is created. This function runs both during server-side rendering and in the client, allowing you to get the necessary data for the page without needing to show a loading spinner and fetching data onMount. This function receives an object as the input, and the value it returns is passed to the page as a prop. If you return a promise, the page will not be rendered until the promise is resolved.

    </div>
    <h1 class="font-bold text-2xl mb-8">Conclusion</h1>
    <div class="mb-8">
      Both Svelte and SvelteKit are extremely intuitive and easy to learn. If you are wondering when to use Svelte vs SvelteKit, I would argue that 99% of the time SvelteKit is the answer. It can do everything Svelte can do and more, making it even more powerful and an overall better developer experience. SvelteKit streamlines the entire stack into a single, file-based layout which is then used to provide a consistent development experience for multiple production environments. SvelteKit provides all the benefits of Svelte, as well as a multitude of end-to-end features for building dynamic, data-driven apps. While SvelteKit is akin to Next.js, it is even more ambitious, and I believe it is the future of web development.

    </div>
    <div class="mt-8 border-t py-8">
      <p class="font-bold mb-2">Written By</p>
      <div class="flex items-center">
        <div class="h-10 w-10 rounded-full bg-cover bg-center mr-4" style="background-image: url(/profile.jpg)"></div>
        <p>Stephanie Dietz</p>
      </div>
    </div>
    <div class="pt-8 border-t text-sm text-gray-500">
      Last Edited on Sept 17th 2021
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
span {
  padding: 0.25rem;
  border-radius: 0.375rem;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  background-color: #E5E7EB;
  font-size: 0.875rem;
  line-height: 1.25rem;
}
</style>
