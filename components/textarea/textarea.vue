<template>
  <div class="mn-textarea">
    <textarea
      class="mn-textarea-control"
      :rows="rows"
      :placeholder="placeholder"
      :readonly="readonly"
      :disabled="disabled"
      @input="changeValue">{{ value }}</textarea>
    <div class="mn-textarea-counter">
      <mn-icon :name="iosGridViewOutline"></mn-icon>
      {{ value ? value.length : 0 }}
      <span v-if="maxLength">
        / {{ maxLength }}
      </span>
    </div>
  </div>
</template>

<script>
  import Element from '../../util/element'
  import Icon from '../icon/icon'
  import iosGridViewOutline from 'vue-human-icons/js/ios/grid-view-outline'

  export default new Element({
    components: {
      [Icon.name]: Icon
    },
    name: 'mn-textarea',
    props: {
      value: {
        type: null,
        default: undefined,
        required: true
      },
      maxLength: {
        type: Number
      },
      rows: {
        type: Number,
        default: 6
      },
      placeholder: {
        type: String
      },
      readonly: {
        type: Boolean,
        default: false
      },
      disabled: {
        type: Boolean,
        default: false
      }
    },
    data () {
      return {
        iosGridViewOutline
      }
    },
    methods: {
      changeValue (event) {
        this.$emit('input', event.target.value)
      }
    }
  })
</script>

<style lang="scss">
  .mn-textarea {
    &-control {
      display: block;
      width: 100%;
      border: none;
      padding: 0;
      background: transparent;
      outline: none;
      -webkit-appearance: none;
      resize: none;
    }

    &-counter {
      border-top: solid 1px #eee;
      padding-top: 0.5rem;
      text-align: right;
    }
  }
</style>
