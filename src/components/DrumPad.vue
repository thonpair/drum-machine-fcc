<template>
  <button class="drum-pad" :id="btnId" v-on:click="play" v-on:keyup="keyPressed">
      {{ name }}
      <audio
            :src="url" class="clip" :id="audioID">
    </audio>
    </button>
</template>

<script>
export default {
    props:{
        name: String,
        url: String,
        keyCode: Number,
        audioID: String,
        btnId: String,
        description: String,
    },
    methods:{
        keyPressed(e){
            if(e.keyCode === this.keyCode){
                this.play()
            }
        },
        play(){
            let audioPlay = document.getElementById(this.audioID);
            audioPlay.play();
            this.$emit('playing', this.description)
        },

    }
}
</script>

<style>

</style>