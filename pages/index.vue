<template lang="pug">
  .container
    .stage
      h1.px-6.py-6.text-center
        span.text-purple-800 Donin
        |Socialmedia Charts und Statistiken
    .card-wrapper
      Card
        template(v-slot:header)
          svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
            path(d='M22.54 6.42a2.78 2.78 0 0 0-1.94-2C18.88 4 12 4 12 4s-6.88 0-8.6.46a2.78 2.78 0 0 0-1.94 2A29 29 0 0 0 1 11.75a29 29 0 0 0 .46 5.33A2.78 2.78 0 0 0 3.4 19c1.72.46 8.6.46 8.6.46s6.88 0 8.6-.46a2.78 2.78 0 0 0 1.94-2 29 29 0 0 0 .46-5.25 29 29 0 0 0-.46-5.33z')
            polygon(points='9.75 15.02 15.5 11.75 9.75 8.48 9.75 15.02')
          .name YouTube
        .list
          ListItem(v-for="artist in youtube" :key="artist.id" :data="artist")
      Card
        template(v-slot:header)
          svg.feather.feather-instagram(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
            rect(x='2' y='2' width='20' height='20' rx='5' ry='5')
            path(d='M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z')
            line(x1='17.5' y1='6.5' x2='17.51' y2='6.5')
          .name Instagram
        .list
          ListItem(v-for="artist in instagram" :key="artist.id" :data="artist")
      Card
        template(v-slot:header)
          svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
            path(d='M9 18V5l12-2v13')
            circle(cx='6' cy='18' r='3')
            circle(cx='18' cy='16' r='3')
          .name TikTok
        .list
          ListItem(v-for="artist in tiktok" :key="artist.id" :data="artist")
      Card
        template(v-slot:header)
          svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
            path(d='M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z')
          .name Twitter
        .list
          ListItem(v-for="artist in twitter" :key="artist.id" :data="artist")
      Card
        template(v-slot:header)
          svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
            path(d='M21 2H3v16h5v4l4-4h5l4-4V2zm-10 9V7m5 4V7')
          .name Twitch
        .list
          ListItem(v-for="artist in twitch" :key="artist.id" :data="artist")

</template>

<script>
import Card from '@/components/atoms/Card'
import Tag from '@/components/atoms/Tag'
import ListItem from '@/components/atoms/ListItem'

export default {
  components: {
    Card,
    Tag,
    ListItem,
  },
  data() {
    return {
      youtube: [],
      instagram: [],
      tiktok: [],
      twitter: [],
      twitch: [],
    }
  },
  async mounted() {
    this.youtube = await this.$axios.$get(
      'https://api.nindo.de/ranks/charts/youtube/rankViews/small'
    )
    this.instagram = await this.$axios.$get(
      'https://api.nindo.de/ranks/charts/instagram/rankLikes/small'
    )
    this.tiktok = await this.$axios.$get(
      'https://api.nindo.de/ranks/charts/tiktok/rankLikes/small'
    )
    this.twitter = await this.$axios.$get(
      'https://api.nindo.de/ranks/charts/twitter/rankLikes/small'
    )
    this.twitch = await this.$axios.$get(
      'https://api.nindo.de/ranks/charts/twitch/rankViewer/small'
    )
  },
}
</script>

<style lang="scss" scoped>
.card-wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
  grid-gap: 16px 24px;
}

.stage {
  font-size: 2.2rem;
  span {
    display: block;
    font-family: 'Pacifico', cursive;
    font-size: 1.8rem;
    font-weight: normal;
  }
  font-weight: bold;
}
</style>
