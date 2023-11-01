<template>
	<div class="music-base">

		<div class="search-bar">
			<input class="music-search">
		</div>

		<div class="music-list-wrapper">

			<music-item
				v-for="music in musicList"
				:key="music.id"
				:music="music"
				@selectMusic="updateMusicPlayer"
			/>

		</div>

	</div>
</template>

<script>
import MusicItem from "./MusicItem.vue";

export default {
  name: "music-base",
  components: {
    MusicItem,
  },
  data() {
    return {
      musicList: [
				{
					id: 1,
					title: "METAMORPHOSIS",
					artist: "INTERWORLD",
					image: "metamorphosis.png",
					audio: "METAMORPHOSIS.mp3"
				},
				{
					id: 2,
					title: "Come as You Phonk",
					artist: "lofi'chield",
					image: "comeasyourphonk.png",
					audio: "ComeAsYouPhonk.mp3"
				},
				{
					id: 3,
					title: "GTG",
					artist: "Freddie Dredd",
					image: "danger.png",
					audio: "GTG.mp3"
				},
				{
					id: 4,
					title: "Criminal Breath",
					artist: "VØJ & ATSMXN",
					image: "criminal.png",
					audio: "CriminalBreath.mp3"
				},
				{
					id: 5,
					title: "MURDER IN MY MIND",
					artist: "KORDHELL",
					image: "murder.png",
					audio: "MURDERINMYMIND.mp3"
				},
				{
					id: 6,
					title: "Override",
					artist: "KSLV",
					image: "override.png",
					audio: "Override.mp3"
				},
				],
      selectedMusic: null, // add a new property to store the selected music
    };
  },
  methods: {
    updateMusicPlayer(music) {
      this.selectedMusic = music; // update the selectedMusic property with the selected track
    },
  },
};
</script>

<style scoped>
.music-list-wrapper::-webkit-scrollbar {
  width: 10px; /* Ширина вертикальной полосы прокрутки */
	border-radius: 10px;
	margin: 20px 20px 20px 0;
}

.music-list-wrapper::-webkit-scrollbar-track {
  background: none; /* Цвет фона полосы прокрутки */
	border-radius: 10px;
	margin: 20px 20px 20px 0;

}

.music-list-wrapper::-webkit-scrollbar-thumb {
	background: rgba(191, 188, 188, 0.33);
	border-radius: 10px;
	margin: 20px 20px 20px 0;

}

.music-list-wrapper::-webkit-scrollbar-thumb:hover {
  background: rgba(191, 188, 188, 0.33);
	border-radius: 10px;
	margin: 20px 20px 20px 0;

}

.music-list-wrapper {
	background: rgba(175, 148, 196, 0.3);
	margin-top: 20px;
  max-height: 460px; /* Установите желаемую максимальную высоту */
  overflow-y: auto; /* Включите вертикальный скролл при необходимости */
	box-shadow: inset 0 0 10px rgba(0, 0, 0, 5);
	border-radius: 15px;
	padding: 10px;
}


.music-list {
  display: flex;
  flex-wrap: wrap; /* Разрешить перенос элементов на новую строку */
  gap: 60px; /* Пространство между элементами */
  justify-content: center; /* Выравнивание по центру горизонтально */
  align-items: center; /* Выравнивание по центру вертикально */
  height: auto; /* Автоматическая высота */
}
.music-base {
	background: rgba(0, 0, 0, 0.3);
  width: 100%;
	padding: 10px;
	margin: 0 15px;
	height: 75vh;
	border-radius: 15px;
	color: aliceblue;
}

.search-bar {
	display: flex;
	justify-content: center;
}
.music-search {
	border-radius: 20px;
	border: none;
	height: 40px;
	width: 600px;
	margin-top: 20px;
	padding-left: 20px;
	outline: none;
	box-shadow: inset 0 0 10px black;
	font-size: medium;
}



</style>