<template>
  <div id="app">
    <div class="banner">
      <img
        src="https://vuejs.org/images/logo.png"
        width="100"
        alt="vue"
        class="logo"
      />
      <h1 v-on:click="prependAdjective()">Welcome to {{name}}</h1>
    </div>
    <div class="bottom">
      Here's number two computed by math.js: {{two()}}
    </div>
  </div>
</template>

<script>
  import * as math from 'mathjs'

  let name = 'Thingamajig'
  let adjectives = [
    'Awesome', 'Epic', 'Cool', 'TotesYeetYo'
  ]

  function randomItem(arr) {
    return arr[Math.floor( Math.random() * arr.length )]
  }

  export default {
    name,

    data() {
      return {
        name
      }
    },

    methods: {
      prependAdjective() {
        this.name = randomItem(adjectives) + this.name
      },

      two() {
        return math.evaluate('1 + 1')
      }
    }
  }
</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>
  code {
    font-family: Menlo, Monaco, Lucida Console, Liberation Mono, DejaVu Sans Mono, Bitstream Vera Sans Mono, Courier New, monospace, serif;
    font-size: 0.9em;
    white-space: pre-wrap;
    color: #2c3e50;
  }

  code::before, code::after {
    content: '`';
  }
</style>

<!-- Scoped component css -->
<!-- It only affect current component -->
<style scoped>
  #app {
    text-align: center;
  }

  #app h1 {
    color: #2c3e50;
    font-weight: 300;
    margin: 0;
  }

  .banner {
    height: 200px;
    background-color: #f6f6f6;
    padding: 50px 10px;
  }

  .bottom {
    padding: 80px 10px;
    font-size: 24px;
    font-weight: 300;
  }

  .fade {
    font-size: 14px;
  }

  .logo {
    animation: spin 4s 1s infinite linear
  }

  @keyframes spin {
    from {transform:rotate(0deg);}
    to {transform:rotate(360deg);}
  }
</style>
