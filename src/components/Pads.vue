<template>
  <g>

    <!-- Q Key -->
    <g @click="handleClick(audio[0])" class="pad">
      <path class="sound"
        :d="soundShape(audio[0])
            ? 'm 57.7,54.6 H 99.0 l -0.3,-1.3 -7.3,-0.0 -3.9,-0.0 -3.2,-0.0 -4.5,-0.0 -4.0,0.0 -3.1,0.1 -5.9,0.0 -9.4,0.0 z'
            : 'm 57.7,54.6 H 99.0 l 4.0,-5.9 -9.7,1.1 -0.0,-5.6 -7.9,4.1 -5.7,-8.3 -5.4,8.3 -8.8,-4.1 0.0,5.6 -11.5,-1.1 z'"
      />
      <rect class="pedal" width="7.4" height="16.2" x="74.9" y="78.2" />
      <circle class="drum" r="1.9" cy="81" cx="78.5" :transform="soundShape(audio[0]) ? 'translate(0 9)' : 'translate(0 0)'" />
      <rect class="bass" width="45.5" height="25.9" x="56" y="53" />
      <text class="key-text" x="77" y="60">{{audio[0].key}}</text>
    </g>

    <!-- E Key -->
    <g @click="handleClick(audio[2])" class="pad">
      <path class="sound" transform="translate(25.5 5)"
        :d="soundShape(audio[2])
            ? 'm 81.2,79.8 3.8,3.5 0.9,5.2 -2.0,4.7 -3.6,3.6 -4.1,1.0 -6.7,-1.2 -2.5,-4.8 -0.5,-4.6 1.6,-3.2 2.4,-4.0 4.3,-1.9 z'
            : 'm 88,68 -2,14 11,3 -11,8 1,11 -9,-3 -13,6 -1,-13 -10,-4 7,-6 -2,-12 16,3 z'"
      />
      <circle class="drum" r="14" cy="92.9" cx="100.2" />
      <text class="key-text" x="99" y="104">{{audio[2].key}}</text>
    </g>

    <!-- C Key -->
    <g @click="handleClick(audio[8])" class="pad">
      <path class="sound" transform="translate(-17 4)"
        :d="soundShape(audio[8])
            ? 'm 80.4,81.0 3.1,2.9 0.7,4.3 -1.6,3.9 -3.0,3.0 -3.4,0.8 -5.6,-1.0 -2.1,-4.0 -0.4,-3.8 1.3,-2.6 2.0,-3.3 3.6,-1.5 z'
            : 'm 84.8,68 0.3,13.6 11.6,4.1 -10,6.3 L 87,104 77.1,99.5 66.6,106.5 65.3,94 54.2,91.3 63.6,83.6 59,72 74,77 Z'"
      />
      <circle class="drum" r="12" cy="91.3" cx="59.1" />
      <text class="key-text" x="58" y="100">{{audio[8].key}}</text>
    </g>

    <!-- W Key -->
    <g @click="handleClick(audio[1])" class="pad">
      <path class="sound" transform="translate(54.5 18)"
        :d="soundShape(audio[1])
            ? 'm 81.2,79.8 3.8,3.5 0.9,5.2 -2.0,4.7 -3.6,3.6 -4.1,1.0 -6.7,-1.2 -2.5,-4.8 -0.5,-4.6 1.6,-3.2 2.4,-4.0 4.3,-1.9 z'
            : 'm 76,65 5,12 13,-4 -8,15 7,9 -9,-1 -10,12 -4,-11 -13,2 4,-14 -5,-9 10,0 z'"
      />
      <circle class="shape" r="16.6" cy="-42.4" cx="162.2" transform="rotate(54)" />
      <path class="highlight" d="m 129.8,106 -16.2,2.9 0.9,2.9 z" />
      <path class="highlight" d="m 129.8,106 -13.4,9.7 2,2.2 z" />
      <path class="highlight" d="m 129.8,106 15,-6.9 -1.6,-2.6 z" />
      <path class="highlight" d="m 129.8,106 8.2,14.3 2.4,-1.8 z" />
      <path class="highlight" d="m 129.8,106 -7.2,-14.9 -2.5,1.6 z" />
      <circle class="stroke" cx="162.2" cy="-42.4" r="16.6" transform="rotate(54)" />
      <circle class="inner-circle" cx="162.2" cy="-42.4" r="1" transform="rotate(54)" />
      <text class="key-text" x="129" y="120">{{audio[1].key}}</text>
    </g>

    <!-- A Key -->
    <g @click="handleClick(audio[3])" class="pad">
      <path class="sound" transform="translate(-42 12)"
        :d="soundShape(audio[3])
            ? 'm 81.2,79.8 3.8,3.5 0.9,5.2 -2.0,4.7 -3.6,3.6 -4.1,1.0 -6.7,-1.2 -2.5,-4.8 -0.5,-4.6 1.6,-3.2 2.4,-4.0 4.3,-1.9 z'
            : 'm 85.2,73.7 -1.7,10.7 8.3,2.7 -8.8,6.2 1.5,8.9 -7.4,-2.8 -10.0,4.8 -1.1,-9.9 -7.9,-3.5 5.6,-5.2 -2.2,-9.3 12.4,2.9 z'"
      />
      <circle class="shape" cx="97.7" cy="-39.3" r="11.3" transform="rotate(93.3)" />
      <path class="highlight" d="m 33.5,99.8 -9.8,-5.5 -0.8,1.9 z" />
      <path class="highlight" d="m 33.5,99.8 -11.3,-0.7 0.1,2 z" />
      <path class="highlight" d="m 33.5,99.8 10.9,2.9 0.3,-2 z" />
      <path class="highlight" d="m 33.5,99.8 -1.9,11.1 2,0.1 z" />
      <path class="highlight" d="M 33.5,99.8 36.2,88.8 34.2,88.5 Z" />
      <circle class="stroke" r="11.3" cy="-39.3" cx="97.7" transform="rotate(93.3)" />
      <circle class="inner-circle" r="0.6" cy="-39.3" cx="97.7" transform="rotate(93.3)" />
      <text class="key-text" x="32" y="109">{{audio[3].key}}</text>
    </g>

    <!-- S Key -->
    <g @click="handleClick(audio[4])" class="pad">
      <path class="sound" transform="translate(16 -19)"
        :d="soundShape(audio[4])
            ? 'm 81.2,79.8 3.8,3.5 0.9,5.2 -2.0,4.7 -3.6,3.6 -4.1,1.0 -6.7,-1.2 -2.5,-4.8 -0.5,-4.6 1.6,-3.2 2.4,-4.0 4.3,-1.9 z'
            : 'm 83.2,71.8 0.3,12.6 8.9,4.0 -9.4,4.9 1.5,8.9 -7.4,-2.8 -10.0,4.8 -0.3,-9.6 -10.8,-2.9 7.7,-6.1 -2.2,-9.3 12.7,3.6 z'"
      />
      <circle  class="drum" r="11.2" cy="68.4" cx="90.8" />
      <text class="key-text" x="90" y="77">{{audio[4].key}}</text>
    </g>

    <!-- X Key -->
    <g @click="handleClick(audio[7])" class="pad">
      <path class="sound" transform="translate(-11 -22)"
        :d="soundShape(audio[7])
            ? 'm 80.4,81.0 3.1,2.9 0.7,4.3 -1.6,3.9 -3.0,3.0 -3.4,0.8 -5.6,-1.0 -2.1,-4.0 -0.4,-3.8 1.3,-2.6 2.0,-3.3 3.6,-1.5 z'
            : 'm 83.4,73.1 -0.4,11.4 8.1,3.1 -8.6,5.2 1.4,8.4 -7.7,-3.0 -8.7,4.9 0.2,-9.7 -10.8,-1.4 8.3,-6.0 -1.2,-10.3 9.1,5.2 z'"
      />
      <circle class="drum" r="10" cy="67.7" cx="64.7" />
      <text class="key-text" x="63" y="75">{{audio[7].key}}</text>
    </g>

    <!-- D Key -->
    <g @click="handleClick(audio[5])" class="pad">
      <path class="sound" transform="translate(46 -20)"
        :d="soundShape(audio[5])
            ? 'm 81.2,79.8 3.8,3.5 0.9,5.2 -2.0,4.7 -3.6,3.6 -4.1,1.0 -6.7,-1.2 -2.5,-4.8 -0.5,-4.6 1.6,-3.2 2.4,-4.0 4.3,-1.9 z'
            : 'm 81.6,76.0 13.3,0.1 -6.3,11.8 4.3,11.1 -9.4,-0.1 -4.3,10.6 -8.3,-9.4 -13.3,0.8 5.5,-11.6 -8.6,-10.9 12.8,-1.3 5.3,-12.3 z'"
      />
      <circle class="shape" cx="-96.9" cy="-100.7" r="16.6" transform="rotate(163)" />
      <path class="highlight" d="m 121.9,68.6 2.6,-16.3 -3,-0.1 z" />
      <path class="highlight" d="m 121.9,68.6 -4.7,-15.8 -2.7,1.2 z" />
      <path class="highlight" d="m 121.9,68.6 1.5,16 2.9,-1 z" />
      <path class="highlight" d="m 121.9,68.6 -16.3,3 0.9,2.9 z" />
      <path class="highlight" d="m 121.9,68.6 16.4,-1.8 -0.7,-2.9 z" />
      <circle class="stroke" r="16.6" cy="-100.7" cx="-96.9" transform="rotate(163)" />
      <circle class="inner-circle" r="1" cy="-100.7" cx="-96.9" transform="rotate(163)" />
      <text class="key-text" x="121" y="82">{{audio[5].key}}</text>
    </g>

    <!-- Z Key -->
    <g @click="handleClick(audio[6])" class="pad">
      <path class="sound" transform="translate(-40 -18)"
        :d="soundShape(audio[6])
            ? 'm 81.2,79.8 3.8,3.5 0.9,5.2 -2.0,4.7 -3.6,3.6 -4.1,1.0 -6.7,-1.2 -2.5,-4.8 -0.5,-4.6 1.6,-3.2 2.4,-4.0 4.3,-1.9 z'
            : 'm 81.6,76.0 13.3,0.1 -6.3,11.8 4.3,11.1 -9.4,-0.1 -4.3,10.6 -8.3,-9.4 -13.3,0.8 5.5,-11.6 -8.6,-10.9 12.8,-1.3 5.3,-12.3 z'"
      />
      <circle class="shape" r="14.5" cy="78.7" cx="-7.8" transform="rotate(-32.8)" />
      <path class="highlight" d="m 36.1,70.4 1.7,14.2 2.5,-0.6 z" />
      <path class="highlight" d="m 36.1,70.4 7.7,12.1 2,-1.6 z" />
      <path class="highlight" d="m 36.1,70.4 -5.2,-13.4 -2.3,1.2 z" />
      <path class="highlight" d="m 36.1,70.4 12.8,-6.4 -1.4,-2.2 z" />
      <path class="highlight" d="m 36.1,70.4 -13.3,5.4 1.2,2.2 z" />
      <circle class="stroke" cx="-7.8" cy="78.7" r="14.5" transform="rotate(-32.8)" />
      <circle class="inner-circle" cx="-7.8" cy="78.7" r="1" transform="rotate(-32.8)" />
      <text class="key-text" x="35" y="82">{{audio[6].key}}</text>
    </g>

  </g>
</template>

<script>
export default {
  name: "Pads",
  props: {
    audio: {
      type: Array,
      required: true
    },
    handleClick: {
      type: Function,
      required: true
    },
    playing: {
      type: String,
      required: true
    }
  },
  methods: {
    soundShape(audio) {
      return this.playing !== audio.name;
    }
  }
};
</script>

<style>
text.key-text {
  font-size: 0.15rem;
  font-family: "New Rocker", cursive;
  fill: #d272df;
}
.pad {
  cursor: pointer;
}
.shape {
  fill: #beb74a;
}

.highlight {
  fill: #e7e5c3;
}

.stroke {
  fill: none;
  stroke: #6a1674;
  stroke-width: 0.5;
}

.inner-circle {
  fill: #1a1815;
}

.drum {
  fill: #fff2fb;
  stroke: #7d208a;
  stroke-width: 1;
}

.bass {
  fill: #6a1674;
  stroke: #fbdcff;
  stroke-width: 1;
}

.pedal {
  fill: #6a1674;
  stroke: none;
}

.sound {
  fill: #ffb100;
  stroke: #fff2fb;
  stroke-width: 1;
  opacity: 1;
  transition: all 100ms;
}
</style>
