<template>
  <div class="search-bar">
    <div class="search-bar-wrapper">
      <van-icon
        class="search"
        name="search"
        color="#858C96"
        size="16px"
      ></van-icon>
      <input
        class="search-bar-input"
        type="text"
        :focus="focus"
        :disabled="disabled"
        :maxlength="limit"
        :placeholder="hotSearch.length === 0 ? '请输入搜索关键字' : hotSearch"
        placeholder-style="color: #ADB4BE"
        v-model="searchWord"
        @change="onChange"
        confirm-type="search"
        @confirm="onConfirm"
      >
      <van-icon
        v-if="searchWord.length > 0"
        class="clear"
        @click="onClearClick"
        name="clear"
        color="#ccc"
        size="16px"
      ></van-icon>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    focus: {
      type: Boolean,
      default: true
    },
    disabled: {
      type: Boolean,
      default: false
    },
    limit: {
      type: Number,
      default: 50
    },
    hotSearch: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      searchWord: ''
    }
  },
  methods: {
    onSearchBarClick() {
      this.$emit('onClick')
    },
    onClearClick() {
      this.searchWord = ''
      this.$emit('onClear')
    },
    onChange(e) {
      const {value} = e.mp.detail
      this.$emit('onChange', value)
    },
    onConfirm(e) {
      const {value} = e.mp.detail
      this.$emit('onConfirm', value)
    },
    setValue(v) {
      this.searchWord = v
    },
    getValue() {
      return this.searchWord
    }
  }
}
</script>

<style lang="scss" scoped>
.search-bar {
  padding: 15px;
  .search-bar-wrapper {
    padding: 13px 15px;
    height: 40px;
    display: flex;
    align-items: center;
    background-color: #F5F7F9;
    box-sizing: border-box;
    border-radius: 40px;
    .search, .clear {
      height: 100%;
      display: flex;
      align-items: center;
    }
    .search-bar-input {
      flex: 1;
      margin: 0 8px;
    }
  }
}
</style>
