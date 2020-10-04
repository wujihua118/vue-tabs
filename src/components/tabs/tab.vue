<script>
export default {
  name: 'Tab',
  data () {
    return {}
  },
  props: {
    label: {
      type: [String, Number],
      default: 'tab'
    },
    index: {
      type: [String, Number],
      default: '1'
    }
  },
  computed: {
    // 索引相等时高亮
    active () {
      return this.index == this.$parent.currentIndex
    }
  },
  methods: {
    clickHandler () {
      this.$parent.onChangeIndex(this.index)
    }
  },
  mounted () {
    // this => 当前组件（tab）
    this.$parent.panes.push(this)
  },
  render () {
    const currentClass = {
      tab: true,
      active: this.active
    }
    return (
      <li class={ currentClass } onClick={ this.clickHandler }>{ this.label }</li>
    )
  }
}
</script>

<style scoped>
  .tab {
    flex: 1;
    list-style: none;
    line-height: 50px;
    position: relative;
    text-align: center;
    cursor: pointer;
    margin-right: 5px;
  }
  .tab:hover {
    background-color: #2296F3;
    color: #fff;
  }
  .tab:last-child {
    margin-right: 0;
  }

  .tab.active {
    color: #fff;
    background-color: #2296F3;
  }
</style>