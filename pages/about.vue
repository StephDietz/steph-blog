<template lang="html">
  <div class="relative flex md:flex-row flex-col px-12 md:px-40 lg:px-60 mt-16 md:mt-24 pb-16 md:pb-24">
    <div class="rocket md:block hidden">
        <nuxt-img
          src="/rocket.png"
          sizes="xl:100vw lg:100vw md:100vw sm:100vw xs:100vw"
          alt="rocket"
          height='200px'
          width='200px'/>
    </div>
    <div class="md:w-2/3 w-full">
      <h1 class="d3 text-4xl mb-12">About Me</h1>
      <div class="mb-4">
        Hey 👋, I'm Steph. I'm a self-taught developer based out of Dallas, Tx.
      </div>
      <div class="mb-4">
        I'm a Baylor grad with a BS in Biochem, but my interest in solving problemas and creating lead me to become a software developer. I work with startups to help create beutiful interfaces, and recently began creating content to expand my knowledge and help build yours!
      </div>
      <div class="">
        I'm always trying to expand my skillset, and beleive the best way to learn is through doing and teching. Follow me on my journey as I share all the tricks I pick up along the way!
      </div>
    </div>
    <!-- <div class="w-1/2 pl-8">
      <div class="w-full bg-red-500" style="height: 50%;">

      </div>
    </div> -->
  </div>
</template>

<script>
export default {
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
.rocket{
  position:absolute;
  bottom:0;
  right:0;
  -webkit-animation: shimmy 4s;animation: shimmy 4s;
  -webkit-animation-direction: alternate;animation-direction: alternate;
}
   @keyframes shimmy {
    0% {
          bottom:0%;
       }
    100%{
          bottom:100%

    }
  }

</style>
