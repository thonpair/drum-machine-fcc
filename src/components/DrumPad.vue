<template>
  <button class="drum-pad" :id="buttonName">
      {{ buttonName }}
      <audio
            src="/media/cc0-audio/t-rex-roar.mp3" class="clip" :id="buttonName">
    </audio>
  </button>
</template>

<script>
export default {
    props:{
        buttonName: String,
    }
}
</script>

<style>
    .drum-pad{

    }
    .clip{

    }
</style>