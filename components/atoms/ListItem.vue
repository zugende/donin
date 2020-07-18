<template lang="pug">
.list-item-wrapper.flex.justify-between.my-4.px-6
  .li-img.bg-gray-300
    img(:src="data.avatar")
    .li-rank.bg-purple-800.flex.justify-center.align-center {{data.rank}}
  .li-name.flex.justify-center.align-start.flex-col
    .real {{data._artist.name}}
    .pseudonym.text-gray-600 @{{data.name}}
  .li-data.flex.justify-start.align-center
    Tag {{miniNumber(data.value)}}
</template>

<script>
import Tag from '@/components/atoms/Tag'

export default {
  components: {
    Tag,
  },
  props: {
    data: {
      type: Object,
      default: null,
    },
  },
  methods: {
    miniNumber(nr) {
      if (nr >= 1000000) {
        return (nr / 1000000).toFixed(1) + 'M'
      } else if (nr >= 1000) {
        return (nr / 1000).toFixed(1) + 'k'
      }
      return nr
    },
  },
}
</script>

<style lang="scss" scoped>
.list-item-wrapper {
  &:hover {
    background-color: rgba(gray, 0.04);
    cursor: pointer;
    .li-img {
      transform: scale(1.1);
    }
  }
}

.li-img {
  transition: all 0.24s ease;
  position: relative;
  height: 96px;
  width: 96px;
  border-radius: 8px;
  img {
    max-width: 96px;
    border-radius: 8px;
  }
  .li-rank {
    position: absolute;
    top: -8px;
    right: -8px;
    height: 24px;
    width: 24px;
    border-radius: 100%;
    color: white;
    font-weight: bolder;
  }
}
.li-name {
  .real {
    font-weight: bold;
  }
}
</style>
