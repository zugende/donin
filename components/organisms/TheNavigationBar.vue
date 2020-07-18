<template lang="pug">
.navigation-bar-wrapper.px-8.bg-purple-800
  .navigation-bar
    .menu-icon(class="md:block lg:hidden")
      svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
        line(x1='3' y1='12' x2='21' y2='12')
        line(x1='3' y1='6' x2='21' y2='6')
        line(x1='3' y1='18' x2='21' y2='18')
    .logo.flex
      .l-name Donin
    .chart.items(class="hidden md:flex justify-around")
      .item
        svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
          path(d='M22.54 6.42a2.78 2.78 0 0 0-1.94-2C18.88 4 12 4 12 4s-6.88 0-8.6.46a2.78 2.78 0 0 0-1.94 2A29 29 0 0 0 1 11.75a29 29 0 0 0 .46 5.33A2.78 2.78 0 0 0 3.4 19c1.72.46 8.6.46 8.6.46s6.88 0 8.6-.46a2.78 2.78 0 0 0 1.94-2 29 29 0 0 0 .46-5.25 29 29 0 0 0-.46-5.33z')
          polygon(points='9.75 15.02 15.5 11.75 9.75 8.48 9.75 15.02')
        .name Youtube
      .item
        svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
          rect(x='2' y='2' width='20' height='20' rx='5' ry='5')
          path(d='M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z')
          line(x1='17.5' y1='6.5' x2='17.51' y2='6.5')
        .name Instagram
      .item
        svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
          path(d='M9 18V5l12-2v13')
          circle(cx='6' cy='18' r='3')
          circle(cx='18' cy='16' r='3')
        .name TikTok
      .item
        svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
          path(d='M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z')
        .name Twitter
      .item
        svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
          path(d='M21 2H3v16h5v4l4-4h5l4-4V2zm-10 9V7m5 4V7')
        .name Twitch
    .chart.items(class="hidden lg:flex justify-around")
      .item
        svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
          polygon(points='12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2')
        .name Viral
      .item
        svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
          line(x1='19' y1='5' x2='5' y2='19')
          circle(cx='6.5' cy='6.5' r='2.5')
          circle(cx='17.5' cy='17.5' r='2.5')
        .name Rabatt
      .item
        svg(xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewbox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round')
          path(d='M4 15s1-1 4-1 5 2 8 2 4-1 4-1V3s-1 1-4 1-5-2-8-2-4 1-4 1z')
          line(x1='4' y1='22' x2='4' y2='15')
        .name 100k
    .search
      SearchInput

</template>

<script>
import SearchInput from '@/components/atoms/SeachInput'

export default {
  components: {
    SearchInput,
  },
}
</script>

<style lang="scss" scoped>
.navigation-bar {
  max-width: 1280px;
  margin: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;

  .menu-icon {
    color: white;
    padding: 8px;
    border-radius: 8px;
    &:hover {
      background-color: rgba(white, 0.08);
      cursor: pointer;
    }
  }

  .logo {
    font-family: 'Pacifico', cursive;
    font-size: 1.4rem;
    color: white;
    max-width: 120px;
  }
}

.items {
  .item {
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 8px;
    margin: 0 8px;
    color: white;
    .name {
      color: rgba(white, 0.64);
      font-size: 14px;
    }
    &:hover {
      background-color: rgba(white, 0.08);
      cursor: pointer;
    }
  }
}
</style>
