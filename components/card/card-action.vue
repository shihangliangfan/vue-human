<template>
  <div class="mn-card-item-action">
    <slot></slot>
  </div>
</template>

<script>
  import Element from '../../util/element'

  export default new Element({
    name: 'mn-card-action'
  })
</script>
