<template>
  <div>
    <span class="msg">
      hello world
    </span>
    <van-button @click="jump" type="primary">按钮</van-button>
  </div>
</template>

<script>
export default {
  methods: {
    jump() {
      this.$router.replace('/pages/index/main')
    }
  }
}
</script>

<style lang="scss" scoped>
  .msg {
    color: red;
    font-size: 20px;
    font-weight: bold;
  }
</style>
