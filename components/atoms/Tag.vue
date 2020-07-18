<template lang="pug">
.tag-wrapper
  span.inline-block.bg-gray-200.rounded-full.px-3.py-1.text-sm.font-semibold.text-gray-700.mr-2
    slot
</template>

<style lang="scss">
.tag-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
