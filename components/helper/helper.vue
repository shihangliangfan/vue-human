<template>
  <div class="mn-helper" v-if="validate.$error">
    <slot></slot>
  </div>
</template>

<script>
  import Element from '../../util/element'

  export default new Element({
    name: 'mn-helper',
    props: {
      validate: Object
    }
  })
</script>
