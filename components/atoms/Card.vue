<template lang="pug">
.rounded.overflow-hidden.shadow-lg.bg-white
  .card-header.py-6.font-bold.text-xl.text-center
    slot(name="header")
  .py-4
    slot

</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.card-header {
  display: flex;
  justify-content: center;
  align-items: center;
  svg {
    margin-right: 16px;
  }
}
</style>
