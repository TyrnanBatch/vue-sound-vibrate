<template>
  <div>
    <button @click="playSoundAndVibrate">Play Sound and Vibrate</button>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  setup() {
    const playSound = () => {
      let audio = new Audio('/sound.mp3');
      audio.play();
    };

    const vibrateDevice = () => {
      if ('vibrate' in navigator) {
        navigator.vibrate(500);
      } else {
        console.log('Vibration API is not supported in this browser.');
      }
    };

    const playSoundAndVibrate = () => {
      playSound();
      vibrateDevice();
    };

    return {
      playSoundAndVibrate,
    };
  },
};
</script>
