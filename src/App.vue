<template>

  <!-- <svg height="400" width="450">
  <path class="path" id="lineAB" v-bind:d="lineDraw" stroke="red"
  stroke-width="3" fill="none" />
  <polyline class="path" v-bind:points="polyDraw"
  style="fill:white;stroke:red;stroke-width:4" />
  </svg> -->
  
<svg version="1.1" id="Floor-1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 1920 1080" style="enable-background:new 0 0 1920 1080;" xml:space="preserve" preserveAspectRatio="xMidYMid meet">
<Map></Map>
<polyline class="path" v-bind:points="polyDraw"
  style="fill:none;stroke:red;stroke-width:4" />
</svg>

<div class="container">

  <button class="m-2 btn btn-primary"  v-on:click="drawEngPath">
      Engineering
  </button>
  <button class="m-2 btn btn-primary"   v-on:click="drawDesignPath">
      Design Lab
  </button>
</div>
  <!-- 
    https://css-tricks.com/svg-line-animation-works/
    -->
</template>

<script>
import Map from './components/Map'


export default {
  name: 'App',
  data(){
    return{
      lineDraw: "",
      lineFill: 'blue',
      polyDraw: "",
			designLabPath: "400,714 630,714  630,569  665,569  665,360",
			engPath: "400,714 1400,714"
    }
  },
  components: {
    Map
  },
  mounted(){
  //   var v = this;
  //   setTimeout ( function() {
  //    console.log('triigerer');
  //    v.polyDraw = v.designLabPath; 
  //  },3);
  },
  computed(){
    
  },
	methods: {
		drawEngPath: function(event){
			if (event) {
        this.polyDraw = this.engPath; 
      }
		},
		drawDesignPath: function(event){
			if (event) {
        this.polyDraw = this.designLabPath; 
      }
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

.path {
  stroke-dasharray: 1000;
  stroke-dashoffset: 1000;
  animation: dash 10s linear infinite;
}

@keyframes dash {
  from {
    stroke-dashoffset: 1000;
  }
  to {
    stroke-dashoffset: 0;
  }
} 
</style>
