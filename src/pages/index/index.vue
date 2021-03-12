<template>
  <div class="home">
    <SearchBar
      disabled
      @onClick="onSearchBarClick"
    />
    <ImageView
      src="https://www.youbaobao.xyz/mpvue-res/big.jpg"
      round
      mode="scaleToFill"
      height="200px"
    />
  </div>
</template>

<script>
import SearchBar from '../../components/home/SearchBar'
import ImageView from '../../components/base/ImageView'

export default {
  components: {SearchBar,ImageView},
  methods: {
    onSearchBarClick() {
      //  跳转到搜索页
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
