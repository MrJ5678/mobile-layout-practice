<template>
  <div class="home-banner" @click="onClick">
    <div
      class="bg-img"
      :style="{backgroundImage: bgImage}"
    >
      <div class="title">{{ title }}</div>
      <div class="sub-title">{{ subTitle }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Banner',
  props: {
    title: String,
    subTitle: String,
    img: String
  },
  computed: {
    bgImage() {
      return 'url(' + this.img + ')'
    }
  },
  methods: {
    onClick() {
      this.$emit('onClick')
    }
  }
}
</script>

<style lang="scss" scoped>
.home-banner {
  margin-top: 20px;
  padding: 0 20px;
  box-sizing: border-box;
  .bg-img {
    width: 100%;
    height: 125px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-radius: 10px;
    background-size: 100% 100%;
    background-repeat: no-repeat;
    .title {
      font-size: 18px;
      color: #fff;
      font-weight: 500;
    }
    .sub-title {
      margin-top: 10px;
      padding: 5px 15px;
      border: 1px solid #fff;
      border-radius: 15px;
      background-color: #4585ff;
      font-size: 14px;
      color: #fff;
    }
  }
}
</style>
