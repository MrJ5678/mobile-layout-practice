<template>
  <div class="home">
    <SearchBar
      disabled
      @onClick="onSearchBarClick"
    />
  </div>
</template>

<script>
import SearchBar from '../../components/home/SearchBar'

export default {
  components: {SearchBar},
  methods: {
    onSearchBarClick() {
      //  跳转到搜索页
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
