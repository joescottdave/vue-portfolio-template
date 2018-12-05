<template>
  <div id="app">
    <StrapHeader/>
    <div class="grid">
    <Card v-bind="specialProject"/>
    <Card v-for="n in projects" v-bind:key="n" :name="n"/>
    </div>
  </div>
</template>

<script>
import Card from './components/Card.vue'
import StrapHeader from './components/StrapHeader.vue'

export default {
  name: 'app',
  components: {
    Card,
    StrapHeader
  },
  data() {
    return {
      projects: ['Project01', 'Project02', 'Project03', 'Project04', 'Project05', 'Project06', 'Project07', 'Project08'],
      specialProject: {name: 'Hello World', desc: 'Greetings to the whole world and everyone in it!', icon: '🌍'}
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 80px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3,1fr);
  grid-template-rows: repeat(auto, 1fr);
  grid-gap: 10px;
  margin: 0 auto;
  max-width: 1000px;
}

@media screen and (max-width: 999px) {
  .grid {
    max-width: 650px;
    grid-template-columns: repeat(2,1fr);
  }
}

@media screen and (max-width: 650px) {
  .grid {
    max-width: 350px;
    grid-template-columns: 100%;
  }
}
</style>
