<script setup>
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  </header>

  <main>
    <h1>Ninja Reaction Timer</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay"/>
  </main>
</template>

<script>
  import Block from './components/Block.vue'  

  export default  {
    name: 'App',
    components: { Block },
    data(){
      return {
        isPlaying: false,
        delay: null
      }
    },
    methods: {
      start(){
        this.delay = 1000 + Math.random() * 5000
        this.isPlaying = true
        console.log(this.delay)
      }
    }
  }
</script>

<style scoped>
header {
  line-height: 1.5;
}


.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
