<script>
  import Element from '../../util/element'
  import MnRadioItem from '../radio/radio-item'

  export default new Element({
    name: 'mn-check-item',
    mixins: [ MnRadioItem ],
    methods: {
      click () {
        if (!this.disabled) {
          this.$emit(
            'input',
            this.value.includes(this.data)
              ? this.value.filter(item => item !== this.data)
              : [ ...this.value, this.data ]
          )
        }
      }
    }
  })
</script>
