<template>
	<div class="music-bar">

		<div class="slider_container_time">

			<div class="current-time">{{ selectedMusic?.currentTime }}</div>
			<input type="range" min="1" max="100" value="0" class="seek_slider" @change="seekTo" />
			<div class="total-duration">{{ selectedMusic?.duration }}</div>

		</div>

		<div class="slider_container_volume">

			<i class="fa fa-volume-down"></i>
			<input type="range" min="1" max="100" value="99" class="volume_slider" @change="setVolume"  />
			<i class="fa fa-volume-up"></i>

		</div>

		<div class="buttons">

			<div class="random-track" @click="randomTrack">
				<i class="fas fa-random fa-2x" title="random"></i>
			</div>

			<div class="prev-track" @click="prevTrack">
				<i class="fa fa-step-backward fa-2x"></i>
			</div>

			<div class="playpause-track" @click="playpauseTrack">
				<i class="fa fa-play-circle fa-3x"></i>
			</div>

			<div class="next-track" @click="nextTrack">
				<i class="fa fa-step-forward fa-2x"></i>
			</div>

			<div class="repeat-track" @click="repeatTrack">
				<i class="fa fa-repeat fa-2x" title="repeat"></i>
			</div>

		</div>

	</div>
</template>


<script>
	export default {
		name: "music-bar",
		props: {
			selectedMusic: Object, 
		},
		methods: {
			seekTo() {
			},
			setVolume() {
			},
		},
	};
</script>

<style scoped>
.music-bar {
background: rgba(0, 0, 0, 0.3);
width: 100%;
height: 20vh;
border-radius: 15px;
display: block;
}

.buttons {
display: flex;
justify-content: space-between;
align-items: center;
color: aliceblue;
max-width: 700px;
margin: 0 auto;
}

.slider_container_time {
display: flex;
justify-content: center;
padding-top: 15px;
color: aliceblue;
align-items: center;
}

.seek_slider{
width: 800px;
margin: 0 20px;
background: linear-gradient(90deg,#F7B8FF, #75DDFF);
-webkit-appearance: none;
border-radius: 15px;
height: 10px;
}	

.seek_slider::-webkit-slider-thumb {
-webkit-appearance: none;
appearance: none;
width: 20px;
height: 20px;
background: aliceblue; /* Цвет ползунка */
border-radius: 50%;
}


.slider_container_volume {
display: flex;
justify-content: center;
padding-top: 15px;
padding-bottom: 15px;
color: aliceblue;
}

.volume_slider{
width: 200px;
margin: 0 20px;
background: linear-gradient(90deg,#75DDFF,#F7B8FF);
-webkit-appearance: none;
border-radius: 15px;
height: 10px;
}

.volume_slider::-webkit-slider-thumb {
-webkit-appearance: none;
appearance: none;
width: 15px;
height: 15px;
background: aliceblue; /* Цвет ползунка */
border-radius: 50%;
}

</style>
