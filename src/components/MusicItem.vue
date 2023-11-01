<template>
  <div class="music-item" @click="playMusic">
    <img :src="require('@/img/' + music.image)" alt="Обложка">
    <div class="music-info">
      <h3>{{ music.title }}</h3>
      <p>{{ music.artist }}</p>
    </div>
    <audio ref="audio" :src="require('@/music/' + music.audio)"></audio>
  </div>
</template>

<script>
export default {
  name: "music-item",
  props: {
    music: Object,
  },
  methods: {
    playMusic() {
      // call a method in the parent component to update the music player
      this.$emit("selectMusic", this.music);
    },
  },
};
</script>

<style scoped>
.music-item {
  display: flex;
	flex-direction: column;
  margin: 10px;
  padding: 10px;
  background: rgba(60, 19, 122, 0.523);
  border-radius: 10px;
	box-shadow: 0 0 5px black;
	width: 200px;
	height: 200px;
}

.music-info {
	margin-top: 20px;
}

.music-item img {
  max-width: 120px; /* Максимальная ширина изображения */
  max-height: 120px; /* Максимальная высота изображения */
  object-fit: cover; /* Масштабирование изображения с сохранением соотношения сторон */
}

</style>
