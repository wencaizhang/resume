<template>
  <div id="app">
    <div class="code"><pre>{{ code }}</pre></div>
    <div v-html="styleCode"></div>
  </div>
</template>

<script>

export default {
  name: 'app',
  data () {
    return {
      code: '',
      finalCode: `
        /* 大家好，我是阿文 */
        body { background: #ccc; }
      `,
    }
  },
  created () {
    let n = 0;
    setInterval(() => {
      this.code = this.finalCode.substring(0, n);
      n++;
    }, 100);
  },
  computed: {
    styleCode () {
      return '<style>' + this.code + '</style>';
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}
pre {
  font-family: Courier New !important;
}
</style>
