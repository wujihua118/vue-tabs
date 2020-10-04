<script>

import Content from './content'

export default {
  name: 'Tabs',
  data () {
    return {
      // 承载content内容
      panes: []
    }
  },
  components: {
    Content
  },
  props: {
    currentIndex: {
      type: [String, Number],
      default: '1'
    }
  },
  methods: {
    onChangeIndex (index) {
      this.$emit('changeIndex', index)
    }
  },
  render () {
    return (
      <div>
        <ul class="tabs-header">{ this.$slots.default }</ul>
        <Content panes={ this.panes }></Content>
      </div>
    )
  }
}
</script>

<style scoped>
  .tabs-header {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
    box-shadow: 2px 2px 2px rgba(0, 0, 0, .15);
  }
</style>