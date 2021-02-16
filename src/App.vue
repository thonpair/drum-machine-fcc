<template>
  <div id="drum-machine">
    
      <DrumPad v-for="padItem in drumpadList"
       :name="padItem.name"
       :key="padItem.name"
       :url="padItem.url"
       :keyCode="padItem.keyCode"
       :audioID="padItem.audioID"
       :btnId="padItem.btnId"
       :description="padItem.description"
       v-on:playing="desc" />
    
    <p id='display'>
    {{ currentAudio }}
    </p>
  </div>
</template>

<script>
import DrumPad from './components/DrumPad.vue'

export default {
  name: 'App',
  components: {
    DrumPad
  },
  data(){
    return{
      drumpadList : [
        {name: 'Q', btnId:'btnQ', audioID:'Q', url:'https://s3.amazonaws.com/freecodecamp/drums/Heater-1.mp3', description:'a', keyCode: 81 },
        {name: 'W', btnId:'btnW', audioID:'W', url:'https://s3.amazonaws.com/freecodecamp/drums/Heater-2.mp3', description:'heater 2', keyCode: 87 },
        {name: 'E', btnId:'btnE', audioID:'E', url:'https://s3.amazonaws.com/freecodecamp/drums/Heater-3.mp3', description:'heater 3', keyCode: 69 },
        {name: 'A', btnId:'btnA', audioID:'A', url:'https://s3.amazonaws.com/freecodecamp/drums/Heater-4_1.mp3', description:'heater 4', keyCode: 65 },
        {name: 'S', btnId:'btnS', audioID:'S', url:'https://s3.amazonaws.com/freecodecamp/drums/Heater-6.mp3', description:'heater 6', keyCode: 83 },
        {name: 'D', btnId:'btnD', audioID:'D', url:'https://s3.amazonaws.com/freecodecamp/drums/Dsc_Oh.mp3', description:'dsc oh', keyCode: 68 },
        {name: 'Z', btnId:'btnZ', audioID:'Z', url:'https://s3.amazonaws.com/freecodecamp/drums/Kick_n_Hat.mp3', description:'kick n hat', keyCode: 90 },
        {name: 'X', btnId:'btnX', audioID:'X', url:'https://s3.amazonaws.com/freecodecamp/drums/RP4_KICK_1.mp3', description:'rp4 kick', keyCode: 88 },
        {name: 'C', btnId:'btnC', audioID:'C', url:'https://s3.amazonaws.com/freecodecamp/drums/Cev_H2.mp3', description:'cev h2', keyCode: 67 },
        ],
        currentAudio: '',
    }  
  },
  methods:{
    desc(currentPlaying){
      this.currentAudio = currentPlaying;
    }
  },
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

#drum-machine{
  width: 70%;
  margin: auto;
}
</style>
