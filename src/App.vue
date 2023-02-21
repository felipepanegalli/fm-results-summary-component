<template>
  <div class="w-full h-full flex lg:items-center justify-center bg-neutral-white">
    <div class="flex flex-col lg:flex-row bg-white w-full lg:w-2/4 lg:h-2/4 shadow-md rounded-none lg:rounded-3xl">

      <div
        class="flex flex-col items-center w-full lg:w-1/2 rounded-b-3xl lg:rounded-3xl shadow p-10 bg-gradient-to-b from-gradientx-light-slate-blue to-gradientx-light-royal-blue">
        <h1 class="text-xl font-bold text-neutral-light-lavander">
          Your Result
        </h1>
        <div class="flex flex-col items-center justify-center mt-10 w-40 h-40 rounded-full
              bg-gradient-to-b from-gradientx-violet-blue to-gradientx-persian-blue">
          <span class="text-white font-black text-5xl py-1">76</span>
          <span class="text-neutral-light-lavander">of 100</span>
        </div>
        <h1 class="text-3xl font-medium text-neutral-white mt-10">Great</h1>
        <p class="text-center mt-4 text-neutral-light-lavander">
          You scored higher than 65% of <br class="hidden lg:inline-block">
          the people who have taken <br class="hidden lg:inline-block">
          these tests.
        </p>
      </div>

      <div class="w-full lg:w-1/2 p-10">
        <h1 class="text-xl font-bold text-neutral-dark-gray-blue">Summary</h1>
        <ul class="list-none">
          <li v-for="(item, i) in categories" :key="i" class="flex justify-between my-3.5 px-2 py-3 rounded-lg"
              :class="`bg-primary-${colors[i]} bg-opacity-10`">
            <span class="flex gap-5 font-bold" :class="`text-primary-${colors[i]}`">
              <img :src="require(`./assets/images/${item.icon}`)" :alt="item.category"/>  {{ item.category }}
            </span>
            <p class="text-gray-400 font-bold">
              <span class="text-neutral-dark-gray-blue">{{ item.score }}</span> / 100
            </p>
          </li>
        </ul>
        <button
          class="bg-neutral-dark-gray-blue w-full h-12 rounded-full mt-10 text-neutral-white cursor-pointer hover:bg-gradientx-light-slate-blue">
          Continue
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import dataJson from '../data.json'

export default {
  name: 'App',
  components: {},
  setup () {
    const categories = dataJson
    const colors = ['light-red', 'orange-yellow', 'green-teal', 'cobalt-blue']
    return {
      categories,
      colors
    }
  }
}
</script>
