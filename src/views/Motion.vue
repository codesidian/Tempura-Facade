<template>
<div>


    <svg-map :map="customTaiwan" 
              :location-class="getLocationClass"
              @mouseover="pointLocation"
              @mouseout="unpointLocation"
              @mousemove="moveOnLocation"
              @focus="focusLocation"
              @click="clickLocation"
    />
   <span class="tooltip" :style="tooltipStyle">{{ pointedLocation }}</span>
   </div>
</template> 

<script>
import Maps from "svg-maps";
import { SvgMap } from "vue-svg-map";
import { getLocationName } from '../utilities'
import jsonSVG from './jsonSVG.json'
var Taiwan = jsonSVG
export default {
    name: 'Motion',
    components: {
        SvgMap
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
			customTaiwan: {
				...Taiwan,
				label: "Custom map label",
				locations: Taiwan.location
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
				position: fixed;
				width: 200px;
				padding: 10px;
				border: 1px solid darkgray;
				background-color: white;
			}

.svg-map__location{
width: 800px;
fill:black;
}
.svg-map__location:hover{
  opacity: 0.75;

}
</style>
