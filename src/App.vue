<template>
  <div id="drum-machine">
    <div id="display">
      <button class="drum-pad" :id="padItem" v-for="padItem in padList"  :key="padItem">
      {{ padItem }}
      <audio
            src="/media/cc0-audio/t-rex-roar.mp3" class="clip" :id="buttonName">
    </audio>
    </button>
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
    
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
