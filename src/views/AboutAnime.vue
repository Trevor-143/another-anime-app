<template>
    <div>
        <h3>{{ this.$route.query.aired }}</h3>
        <h3>{{ this.$route.query.type }}</h3>
        <h3>{{ this.$route.query.time }}</h3>
        <h3>{{ this.$route.query.animeStudio }}</h3>
        <h3>{{ this.$route.query.animeType }}</h3>
        <h3>{{ this.$route.query.episodes }}</h3>
        <img :src="this.$route.query.imageOne" :alt="this.$route.query.title">
        <img :src="this.$route.query.imageTwo" :alt="this.$route.query.title">
        <img :src="this.$route.query.imageThree" :alt="this.$route.query.title">
        <!-- <h3>{{ this.$route.query.imageOne }}</h3>
        <h3>{{ this.$route.query.imageTwo }}</h3>
        <h3>{{ this.$route.query.imageThree }}</h3> -->
        <h3>{{ this.$route.query.rating }}</h3>
        <h3>{{ this.$route.query.score }}</h3>
        <h3>{{ this.$route.query.source }}</h3>
        <h3>{{ this.$route.query.status }}</h3>
        <h3>{{ this.$route.query.studio }}</h3>
        <h3>{{ this.$route.query.title }}</h3>
        <img :src="this.$route.query.youTudeImage" :alt="this.$route.query.title">
        <!-- <h3>{{ this.$route.query.youTudeImage }}</h3> -->
        <h3>{{ this.$route.query.description }}</h3>
    </div>
</template>

<script>
    export default {
        name: 'AboutAnime'
    }
</script>
<!-- 
name
aired
type
time
episodes
imageOne
imageTwo
imageThree
rating
score
source
status
studio
title
youTudeImage
description -->