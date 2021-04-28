<template>
  <div class="home-card">
    <div class="home-card-inner">
      <div class="user-info">
        <div class="avatar-wrapper">
          <ImageView
            src="https://www.youbaobao.xyz/mpvue-res/logo.jpg"
            round
          />
        </div>
        <div class="nickname">{{ '隆冬' }}</div>
        <div class="shelf-text">书架共有{{ 3 }}本好书</div>
        <div class="round-item"></div>
        <div class="shelf-text">特别精选</div>
      </div>
      <div class="book-info">
        <div class="book-wrapper">
          <div class="book-img-wrapper">
            <ImageView
              src="https://www.youbaobao.xyz/book/res/img//EarthSciences/978-981-10-3713-9_CoverFigure.jpg"
            />
          </div>
          <div class="book-img-wrapper">
            <ImageView
              src="https://www.youbaobao.xyz/book/res/img//EarthSciences/978-981-10-3713-9_CoverFigure.jpg"
            />
          </div>
          <div class="book-img-wrapper">
            <ImageView
              src="https://www.youbaobao.xyz/book/res/img//EarthSciences/978-981-10-3713-9_CoverFigure.jpg"
            />
          </div>
        </div>
        <div class="shelf-wrapper">
          <div class="shelf">书架</div>
          <van-icon class="arrow" name="arrow" size="11px" color="#828489"/>
        </div>
      </div>
      <div class="feedback-wrapper">
        <span @click="onFeedBackClick">反馈</span>
      </div>
    </div>
    <van-dialog id="van-dialog"></van-dialog>
  </div>
</template>

<script>
import ImageView from './ImageView'
import Dialog from 'vant-weapp/dist/dialog/dialog'

export default {
  name: 'homeCard',
  components: {ImageView},
  props: {
    data: Object,
    hasSign: {
      type: Boolean,
      default: false
    },
    signDay: {
      type: Number,
      default: 0
    }
  },
  methods: {
    gotoShelf() {},
    onBookClick() {},
    sign() {},
    onFeedBackClick() {
      Dialog.confirm({
        title: '反馈',
        message: '您是否确认提交反馈信息？',
        confirmButtonText: '是',
        cancelButtonText: '否'
      }).then(() => {
        console.log('点击是之后')
      }).catch(() => {
        console.log('点击否之后')
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.home-card {
  padding: 7px 20px 0 20px;
  .home-card-inner {
    position: relative;
    padding: 21.5px 17px 20px 20px;
    background-image: linear-gradient(-90deg, #54575F 0%, #595B60 100%);
    border-radius: 15px;
    box-sizing: border-box;
    .user-info {
      display: flex;
      align-items: center;
      .avatar-wrapper {
        height: 20px;
        width: 20px;
        margin-right: 8.5px;
      }
      .nickname {
        margin-right: 8.5px;
        font-family: PingFangSC-Regular;
        font-size: 12px;
        color: #FFFFFF;
        text-align: center;
      }
      .shelf-text {
        margin-right: 5px;
        opacity: 0.7;
        font-family: PingFangSC-Regular;
        font-size: 12px;
        color: #FFFFFF;
        text-align: center;
      }
      .round-item {
        margin-right: 8px;
        width: 4px;
        height: 4px;
        border-radius: 50%;
        background: #A2A2A2;
      }
    }
    .book-info {
      margin-top: 16.5px;
      display: flex;
      justify-content: space-between;
      .book-wrapper {
        flex: 1;
        display: flex;
        justify-content: space-between;
        .book-img-wrapper {
          width: 72px;
          height: 101px;
        }
      }
      .shelf-wrapper {
        margin-left: 17.5px;
        display: flex;
        align-items: center;
        .shelf {
          width: 11px;
          color: #FFFFFF;
          text-align: center;
          font-size: 10.5px;
          word-break: break-word;
          opacity: 0.8;
          margin-right: 9px;
        }
      }
    }
    .feedback-wrapper {
      position: absolute;
      width: 44.5px;
      height: 23.5px;
      line-height: 23.5px;
      top: 19.5px;
      right: 0;
      //padding: 8px 10.5px 4px 12px;
      background: #707070;
      //opacity: 0.3;
      text-align: center;
      z-index: 1;
      border-radius: 100px 0 0 100px;
      font-size: 11px;
      color: #FFFFFF;
    }
  }
}
</style>
