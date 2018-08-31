<template>
  <svg viewBox="0 0 160 100" id="drumkit">
    <g transform="translate(0 -35)">
      <text id="text-display" x="78" y="120">{{this.display}}</text>
      <Pads :audio="this.keys" :handleClick="this.handleClick" :playing="this.playing" />
    </g>
  </svg>
</template>

<script>
import Pads from "./Pads";

export default {
  name: "DrumKit",
  components: {
    Pads
  },
  data() {
    return {
      keys: null,
      display: null,
      playing: ""
    };
  },
  methods: {
    handleClick(key) {
      const currKey = this.keys.find(k => k.code === key.code);
      this.playSound(currKey);
      setTimeout(() => {
        this.display = null;
        this.playing = "";
      }, 300);
    },
    handleKeyDown(e) {
      const currKey = this.keys.find(key => key.code === e.keyCode);
      if (!currKey) return;
      this.playSound(currKey);
    },
    handleKeyUp(e) {
      const currKey = this.keys.find(key => key.code === e.keyCode);
      if (!currKey) return;
      this.display = null;
      this.playing = "";
    },
    playSound(currKey) {
      currKey.sound.currentTime = 0;
      currKey.sound.play();
      this.display = currKey.name;
      this.playing = currKey.name;
    }
  },
  beforeMount() {
    document.addEventListener("keydown", this.handleKeyDown);
    document.addEventListener("keyup", this.handleKeyUp);
    this.keys = [
      {
        name: "Boom",
        code: 81,
        key: "Q",
        sound: new Audio("audio/boom.wav")
      },
      {
        name: "Ride 2",
        code: 87,
        key: "W",
        sound: new Audio("audio/ride.wav")
      },
      {
        name: "Kick",
        code: 69,
        key: "E",
        sound: new Audio("audio/kick.wav")
      },
      {
        name: "Hi Hat",
        code: 65,
        key: "A",
        sound: new Audio("audio/hihat.wav")
      },
      {
        name: "Snare",
        code: 83,
        key: "S",
        sound: new Audio("audio/snare.wav")
      },
      {
        name: "Ride 1",
        code: 68,
        key: "D",
        sound: new Audio("audio/ride.wav")
      },
      {
        name: "Open Hat",
        code: 90,
        key: "Z",
        sound: new Audio("audio/openhat.wav")
      },
      {
        name: "Tink",
        code: 88,
        key: "X",
        sound: new Audio("audio/tink.wav")
      },
      {
        name: "Tom",
        code: 67,
        key: "C",
        sound: new Audio("audio/tom.wav")
      }
    ];
  },
  beforeDestroy() {
    document.removeEventListener("keydown", this.handleKeyDown);
  }
};
</script>

<style>
#drumkit {
  max-width: 1200px;
  background: #b845c6;
  background: -moz-radial-gradient(
    center,
    ellipse cover,
    #b845c6 0%,
    transparent 100%
  );
  background: -webkit-radial-gradient(
    center,
    ellipse cover,
    #b845c6 0%,
    transparent 100%
  );
  background: radial-gradient(ellipse at center, #b845c6 0%, transparent 100%);
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#b845c6', endColorstr='transparent',GradientType=1 );
  border: 1px solid #b845c6;
}

#text-display {
  text-anchor: middle;
  font-family: "New Rocker", cursive;
  font-size: 0.3rem;
  fill: #f187ff;
}
</style>
