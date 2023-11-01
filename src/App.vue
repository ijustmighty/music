<template>
	<div class="new-app">
		<div class="music-app">
			<!-- <music-menu></music-menu>  -->
			<!-- <music-info></music-info> -->
			<music-base/>
		</div>
		<div class="music-bars">
			<music-bar/>
		</div>
	</div>

</template>

<script>
// import MusicMenu from './components/MusicMenu.vue';
// import MusicInfo from './components/MusicInfo.vue'; 
import MusicBase from './components/MusicBase.vue';
import MusicBar from './components/MusicBar.vue';

export default {
	components: {
		// 'music-menu': MusicMenu, 
		// 'music-info': MusicInfo,
		'music-base': MusicBase,
		'music-bar': MusicBar,
	},
}
</script>

<style>

.new-app {
	background: linear-gradient(180deg, #672fa0, #3167BF);
}

.music-app {
	height: 100%;
	padding: 15px;
	display: flex;
	justify-content: space-between;
}

.music-bars {
	justify-content: center;
	padding: 0 15px 15px 15px;
}

</style>
