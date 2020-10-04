<script>
export default {
  name: 'Content',
  data () {
    return {}
  },
  props: {
    panes: {
      type: Array,
      required: true
    }
  },
  render () {
    return (
      <div>
        {
          this.panes.map((element, index) => {
            return <div>{ element.active ? element.$slots.default : '' }</div>
          })
        }
      </div>
    )
  }
}
</script>