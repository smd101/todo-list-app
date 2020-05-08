<template>
  <div>
    <div class="container">
      <div class="timer">
        <p class="timer-item minutes">{{ minutes }}</p>
        <p class="timer-item seconds">{{ seconds }}</p>
      </div>
    </div>
  <v-row align="center">
    <v-col class="text-center" cols="12" sm="4">
      <div class="my-2">
        <b-button size="lg" variant="outline-primary" v-on:click="start" v-if="!isRunning">START</b-button>
        <b-button size="lg" variant="outline-primary" v-on:click="stop" v-if="isRunning">STOP</b-button>

      </div>
    </v-col>
  </v-row>
  </div>
</template>

<script>
const zeroPadding = (num, digit) => {
  return (Array(digit).join("0") + num).slice(-digit)
}
export default {
  props: ["location", "diff"],
  data() {
    return {
      min: 25,
      sec: 0,
      isRunning: false,
      timerObj: null,
    }
  },
  computed: {
    minutes() {
      return zeroPadding(this.min, 2)
    },
    seconds() {
      return zeroPadding(this.sec, 2)
    },
  },
  methods: {
    count: function() {
      if (this.sec <= 0 && this.min >= 1) {
        this.min --;
        this.sec = 59;
      } else if(this.sec <= 0 && this.min <= 0) {
        this.complete();
      } else {
        this.sec --;
      }
    },

    start: function() {
      let self = this;
      this.timerObj = setInterval(function() {self.count()}, 1000)
      this.isRunning = true; 
    },

    stop: function() {
      clearInterval(this.timerObj);
      this.isRunning = false; 
    },

    complete: function() {
      clearInterval(this.timerObj)
    },

  },
}
</script>

<style scoped>
.container {
  background-color: #3a4a5e;
  padding: 4%;
}
.timer {
  display: flex;
}
.timer-item {
  display: flex;
  justify-content: center;
  align-items: center;
  flex: 1 1;
  height: 100px;
  position: relative;
  z-index: 1;
  padding: 0.5em;
  margin: 3px;
  color: #fff;
  font-family: 'Roboto Mono', monospace;
  font-size: 6rem;
  line-height: 1;
  background-color: #48b883;
  box-sizing: border-box;
}
.timer-item:before {
  position: absolute;
  right: 5px;
  bottom: 1px;
  z-index: 1;
  color: #3a4a5e;
  font-family: 'Teko', sans-serif;
  font-size: 1.4rem;
  letter-spacing: .05em;
}
.minutes:before {
  content: "Minutes";
}
.seconds:before {
  content: "Seconds";
}
</style>