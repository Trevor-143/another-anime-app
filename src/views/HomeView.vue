<template>
  <div class="home">
    <h2>Home</h2>

    <div class="Anime">
      <div class="AnimeList">
        <router-link :to="{
          path: '/about/'+ anime.mal_id,
          query: {
            name: anime.title,
            aired: anime.aired.string,
            time: anime.duration,
            episodes: anime.episodes,
            imageOne: anime.images.webp.small_image_url,
            imageTwo: anime.images.webp.image_url,
            imageThree: anime.images.webp.large_image_url,
            genres: topGenres,
            producers: topProducers,
            rating: anime.rating,
            score: anime.score,
            source: anime.source,
            status: anime.status,
            title: anime.title_english,
            youTudeImage: anime.trailer.images.maximum_image_url,
            description: anime.synopsis,
            themes: topThemes,
            animeStudio: studio,
            animeType: animeType
          }
        }" class="animeListItem" v-for="anime in topAnime" :key="anime.mal_id">
          <img :src="anime.images.webp.image_url" :alt="anime.title">
        </router-link>
      </div>
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
import { ref, onBeforeMount } from "vue";

export default {
  name: 'HomeView',
  components: {
    
  },
  setup() {
    const topAnime = ref([])
    const topGenres = ref([])
    const topProducers = ref([])
    const topThemes = ref([])
    const studio = ref('')
    const animeType = ref('')

    onBeforeMount(() => {
      fetch(`https://api.jikan.moe/v4/top/anime`)
      .then(res => res.json())
      .then(data => {
        console.log(data)
        topAnime.value = data.data
        topGenres.value = data.data.genres
        topProducers.value = data.data.producers
        topThemes.value = data.data.themes
        // studio.value = data.data.studio[0].name
        animeType.value = data.data.demographics
        console.log(animeType.value)
      })
    })
    return {
      topAnime,
      topGenres,
      topProducers,
      topThemes,
      studio,
      animeType
    }
  }
}
</script>
