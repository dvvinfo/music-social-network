<template>
  <div class="bg-green-500 rounded">
    <div id="aplayer" class="i"></div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue'
import APlayer from 'aplayer'
import 'aplayer/dist/APlayer.min.css'

onMounted(() => {
  player()
})

const player = () => {
  new APlayer({
    container: document.getElementById('aplayer'),
    audio: [
      {
        name: 'celine-dion-qui-peut-vivre-sans-amour',
        artist: 'celine dion',
        url: '/music/celine-dion-qui-peut-vivre-sans-amour.mp3',
        cover: 'cover.jpg'
      },
      {
        name: 'coldplay-a-sky-full-of-stars',
        artist: 'coldplay',
        url: '/coldplay-a-sky-full-of-stars.mp3',
        cover: 'cover.jpg'
      },
      {
        name: 'enrique-iglesias-be-with-you',
        artist: 'enrique',
        url: '/enrique-iglesias-be-with-you.mp3',
        cover: 'cover.jpg'
      },
      {
        name: 'evanescence-bring-me-to-life',
        artist: 'evanescence',
        url: '/evanescence-bring-me-to-life.mp3',
        cover: 'cover.jpg'
      },
      {
        name: 'sia-chandelier',
        artist: 'sia',
        url: '/sia-chandelier.mp3',
        cover: 'cover.jpg'
      }
    ]
  })
}
</script>

<style lang="scss" scoped></style>
