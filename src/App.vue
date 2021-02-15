<template>
  <div id="drum-machine">
    <div id="display">
      <DrumPad :buttonName="padItem"  v-for="padItem in padList" :key="padItem" />
    </div>
  </div>
</template>

<script>
import DrumPad from './components/DrumPad'

export default {
  name: 'App',
  components: {
    DrumPad
  },
  data(){
    return{
      padList : ['Q','W','E','A', 'S', 'D', 'Z', 'X', 'C']
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
