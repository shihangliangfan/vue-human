<template>
  <div class="mn-card-media">
    <slot></slot>
  </div>
</template>

<script>
  import Element from '../../util/element'

  export default new Element({
    name: 'mn-card-media'
  })
</script>

<style lang="scss">
  .mn-card-media {
    > img {
      display: block;
      width: 100%;
    }
  }
</style>
