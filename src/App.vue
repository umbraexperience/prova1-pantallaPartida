<template>
  <div id="app">
    <h2>{{ counter }}</h2>

    <button @click="$refs.plyr.player.play()">PLAY</button>
    <button @click="$refs.plyr.player.pause()">PAUSE</button>
    <button @click="$refs.plyr.player.currentTime = 25">Segon 25</button>

    <vue-plyr ref="plyr" :options="{ controls: [''] }">
      <div class="plyr__video-embed">
        <iframe
          src="https://player.vimeo.com/video/76979871?loop=false&byline=false&portrait=false&title=false&speed=true&transparent=0&gesture=media"
          allowfullscreen
          allowtransparency
          allow="autoplay"
        ></iframe>
        <button
          @click="$refs.plyr.player.currentTime = 37"
          class="button-absolute"
        ></button>
      </div>
    </vue-plyr>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    // HelloWorld
  },
  data: function() {
    return {
      counter: 0
    };
  },
  mounted() {},
  computed: {}
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.plyr__video-embed {
  position: relative;
}
.button-absolute {
  position: absolute;
  left: 0px;
  top: 0px;
  font-size: 13rem;
  height: 100%;
  width: 50% !important;
  background-color: transparent;
  color: white;
  border: none;
}

.button-absolute:hover {
  background-color: rgba(255, 255, 255, 0.3);
}

.button-absolute:active {
  background-color: rgba(255, 255, 255, 0.5);
  border: 2px solid white;
}
</style>
