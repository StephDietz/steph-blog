<template lang="html">
  <div class="bg-gray-50 shadow">
    <div class="w-full flex overflow-auto ">
      <div v-for="(tab, i) in tabs" @click="selectedTab = i" :class="`${selectedTab === i ? 'bg-white border-indigo-500' : 'border-transparent'} md:text-base text-xs border-t-2 p-4 `">
        {{ tab.name }}
      </div>
    </div>
    <div class="p-6 bg-white font-mono">
      <div ref="codeBlock" class="rounded-md bg-gray-100 p-6 whitespace-nowrap overflow-auto flex-none overflow-x-scroll">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['tabs'],
  data() {
    return {
      selectedTab: 0
    }
  },
  mounted() {
    this.setHtml()
  },
  methods: {
    setHtml() {
      this.$refs.codeBlock.innerHTML = this.tabs[this.selectedTab].code
    }
  },
  watch: {
    selectedTab() {
      this.setHtml()
    }
  }
}
</script>

<style lang="css" scoped>
</style>
