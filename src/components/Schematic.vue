<template>
<div>

               <svg-map style="" :map="customSchematic" 
                    :location-class="getLocationClass"
                    @mouseover="pointLocation"
                    @mouseout="unpointLocation"
                    @mousemove="moveOnLocation"
                    @focus="focusLocation"
                    @click="clickLocation"
          >

          </svg-map>
              <span class="tooltip" :style="tooltipStyle">{{ pointedLocation }}</span>
</div>
</template>

<script>

import { SvgMap } from "vue-svg-map";
import { getLocationName } from '../utilities'


export default {
    name: 'Motion',
    components: {
        SvgMap
    },
    props:{
      svgjson:[Object]
    },

    mounted(){
      console.log();
    },
    	methods: {
		pointLocation(event) {
			this.pointedLocation = getLocationName(event.target)
		},
		unpointLocation(event) {
			this.pointedLocation = null
			this.tooltipStyle = { display: 'none' }
		},
		moveOnLocation(event) {
			this.tooltipStyle = {
				display: 'block',
				top: `${event.clientY + 10}px`,
				left: `${event.clientX - 100}px`,
			}
    },
    clickLocation(event) {
			this.clickedLocation = getLocationName(event.target);
      alert(event.target.id);
    },
    focusLocation(event) {
			this.focusedLocation = getLocationName(event.target)
		},
		getLocationClass(location, index) {
			return `svg-map__location`
		},
    },
    data() {
        return {
			customSchematic: {
				...this.svgjson,
				label: "Our House",
				locations: this.svgjson.location
      },
      pointedLocation: null,
      tooltipStyle: null,
      focusedLocation: null,
        };
    },
};
</script>

<style>
.tooltip {
        display:none;
				position: fixed;
				width: 200px;
				padding: 10px;
				border: 1px solid darkgray;
				background-color: white;
			}

svg,
img {
  display: block;
  width:100%;
  max-width: 100%;
  max-height:100%;
  height: auto;
}
.svg-map__location{
fill:rgb(128, 128, 128);
}
.svg-map__location:hover{
  opacity: 0.75;
}
</style>
