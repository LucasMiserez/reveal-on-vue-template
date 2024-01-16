<script setup>
import { onMounted } from 'vue'
import Reveal from 'reveal.js'
import Markdown from 'reveal.js/plugin/markdown/markdown.js'
import Highlight from 'reveal.js/plugin/highlight/highlight.js'
import 'reveal.js/dist/reveal.css'
import 'reveal.js/dist/theme/black.css'
import 'reveal.js/plugin/highlight/monokai.css'
import SlideComponent from '@/components/SlideComponent.vue'
import SlideComponentVertical from "@/components/SlideComponentVertical.vue";

onMounted(() => {
  Reveal.initialize({
    plugins: [Markdown, Highlight],
    markdown: {
      breaks: true,
      gfm: true
    }
  })
})
</script>

<template>
  <div id="app">
    <div class="reveal">
      <div class="slides">
        <section data-markdown>
          <SlideComponent />
        </section>
        <section>
          <section data-markdown>
            <textarea data-template>
            ## This is a vertical slide
            </textarea>
          </section>
          <section><SlideComponentVertical /></section>
        </section>
      </div>
    </div>
  </div>
</template>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  height: 90vh;
}
</style>
