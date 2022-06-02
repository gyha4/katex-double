<template>
  <textarea v-model="input"></textarea>
  <div v-html="output"></div>
</template>

<script>

var md = require('markdown-it')();
md.use(require('markdown-it-texmath'), { engine: require('katex') });

export default {
  name: 'App',
  data() {
    return {
      input: '$\\alpha$\n$$\\alpha$$',
    }
  },
  computed: {
    output() {
      return md.render(this.input);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
