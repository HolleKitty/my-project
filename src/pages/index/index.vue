<template>
  <view>
    <view class="top-title">
      <view class="welcome-title">早上好！张三先生</view>
      <view class="bell-tips uni-bg-pink">
        <p>铃铛</p>
      </view>
    </view>
    <view class="uni-margin-wrap">
      <swiper
        class="swiper"
        circular
        :indicator-dots="indicatorDots"
        :autoplay="autoplay"
        :interval="interval"
        :duration="duration"
      >
        <swiper-item>
          <view class="swiper-item uni-bg-red">A</view>
        </swiper-item>
        <swiper-item>
          <view class="swiper-item uni-bg-green">B</view>
        </swiper-item>
        <swiper-item>
          <view class="swiper-item uni-bg-blue">C</view>
        </swiper-item>
      </swiper>
    </view>

    <!-- <view class="swiper-list">
      <view class="uni-list-cell uni-list-cell-pd">
        <view class="uni-list-cell-db">指示点</view>
        <switch :checked="indicatorDots" @change="changeIndicatorDots" />
      </view>
      <view class="uni-list-cell uni-list-cell-pd">
        <view class="uni-list-cell-db">自动播放</view>
        <switch :checked="autoplay" @change="changeAutoplay" />
      </view>
    </view>

    <view class="uni-padding-wrap">
      <view class="uni-common-mt">
        <text>幻灯片切换时长(ms)</text>
        <text class="info">{{ duration }}</text>
      </view>
      <slider @change="durationChange" :value="duration" min="500" max="2000" />
      <view class="uni-common-mt">
        <text>自动播放间隔时长(ms)</text>
        <text class="info">{{ interval }}</text>
      </view>
      <slider @change="intervalChange" :value="interval" min="2000" max="10000" />
    </view> -->
    <!--uni-padding-wrap -->
    <view class="main-content">
      <view class="main-title">
        <view class="menu-item uni-bg-red">
          <view class="item-image">图片</view>
          <p>功能1</p>
        </view>
        <view class="menu-item uni-bg-green" @click="confirmDialog">
          <view class="item-image">图片</view>
          <p>功能2</p>
        </view>
        <view class="menu-item uni-bg-blue">
          <view class="item-image">图片</view>
          <p>功能3</p>
        </view>
        <view class="menu-item uni-bg-pink">
          <view class="item-image">图片</view>
          <p>功能4</p>
        </view>
        <view class="menu-item uni-bg-orange">
          <view class="item-image">图片</view>
          <p>功能5</p>
        </view>
      </view>
      <view class="grid-box">
        <view class="main-list uni-row">
          <view class="grid-item uni-bg-red">
            <view class="item-image">图片</view>
            <p>功能A</p>
          </view>
          <view class="grid-item uni-bg-green">
            <view class="item-image">图片</view>
            <p>功能B</p>
          </view>
          <view class="grid-item uni-bg-blue">
            <view class="item-image">图片</view>
            <p>功能C</p>
          </view>
          <view class="grid-item uni-bg-pink">
            <view class="item-image">图片</view>
            <p>功能D</p>
          </view>
          <view class="grid-item uni-bg-pink">
            <view class="item-image">图片</view>
            <p>功能E</p>
          </view>
          <view class="grid-item uni-bg-red">
            <view class="item-image">图片</view>
            <p>功能F</p>
          </view>
          <view class="grid-item uni-bg-green">
            <view class="item-image">图片</view>
            <p>功能G</p>
          </view>
          <view class="grid-item uni-bg-blue">
            <view class="item-image">图片</view>
            <p>功能H</p>
          </view>
          <view class="grid-item uni-bg-blue">
            <view class="item-image">图片</view>
            <p>功能I</p>
          </view>
          <view class="grid-item uni-bg-pink">
            <view class="item-image">图片</view>
            <p>功能J</p>
          </view>
        </view>
      </view>
    </view>
    <tabbar :current="1"></tabbar>

    <uni-popup ref="popup" type="dialog">
      <view class="menu-box-popup">
        <view class="popup-menu-title">功能B</view>
        <view class="popup-main-list uni-row">
          <view class="popup-menu-item uni-bg-red">
            <view class="item-image">图片</view>
            <p>功能A</p>
          </view>
          <view class="popup-menu-item uni-bg-green">
            <view class="item-image">图片</view>
            <p>功能B</p>
          </view>
          <view class="popup-menu-item uni-bg-blue">
            <view class="item-image">图片</view>
            <p>功能C</p>
          </view>
          <view class="popup-menu-item uni-bg-pink">
            <view class="item-image">图片</view>
            <p>功能D</p>
          </view>
          <view class="popup-menu-item uni-bg-pink">
            <view class="item-image">图片</view>
            <p>功能E</p>
          </view>
          <view class="popup-menu-item uni-bg-red">
            <view class="item-image">图片</view>
            <p>功能F</p>
          </view>
          <view class="popup-menu-item uni-bg-green">
            <view class="item-image">图片</view>
            <p>功能G</p>
          </view>
          <view class="popup-menu-item uni-bg-blue">
            <view class="item-image">图片</view>
            <p>功能H</p>
          </view>
          <view class="popup-menu-item uni-bg-blue">
            <view class="item-image">图片</view>
            <p>功能I</p>
          </view>
          <view class="popup-menu-item uni-bg-pink">
            <view class="item-image">图片</view>
            <p>功能J</p>
          </view>
        </view>
      </view>
    </uni-popup>
    <uni-popup ref="popupDialog" type="dialog"> 123 </uni-popup>
  </view>
</template>

<script>
import tabbar from "@/component/tabbar.vue";
import uniPopup from "@/component/uni-popup/uni-popup.vue";
import uniPopupDialog from "@/component/uni-popup-dialog/uni-popup-dialog.vue";
export default {
  data() {
    return {
      background: ["color1", "color2", "color3"],
      indicatorDots: true,
      autoplay: true,
      interval: 2000,
      duration: 500,
    };
  },
  components: {
    tabbar,
    uniPopup,
    uniPopupDialog,
  },
  methods: {
    confirmDialog() {
      this.$refs.popup.open("center");
      console.log(this.$refs);
      //   this.$refs.popupDialog.open();
    },
    changeIndicatorDots(e) {
      this.indicatorDots = !this.indicatorDots;
    },
    changeAutoplay(e) {
      this.autoplay = !this.autoplay;
    },
    intervalChange(e) {
      this.interval = e.target.value;
    },
    durationChange(e) {
      this.duration = e.target.value;
    },
  },
};
</script>
<style>
.uni-margin-wrap {
  width: 690rpx;
  width: 100%;
}
.swiper {
  height: 300rpx;
}
.swiper-item {
  display: block;
  height: 300rpx;
  line-height: 300rpx;
  text-align: center;
}
.swiper-list {
  margin-top: 40rpx;
  margin-bottom: 0;
}
.uni-common-mt {
  margin-top: 60rpx;
  position: relative;
}
.info {
  position: absolute;
  right: 20rpx;
}
.uni-padding-wrap {
  width: 550rpx;
  padding: 0 100rpx;
}

.flex-item {
  width: 33.3%;
  height: 200rpx;
  text-align: center;
  line-height: 200rpx;
}

.flex-item-V {
  width: 100%;
  height: 150rpx;
  text-align: center;
  line-height: 150rpx;
}

.text {
  margin: 15rpx 10rpx;
  padding: 0 20rpx;
  background-color: #ebebeb;
  height: 70rpx;
  line-height: 70rpx;
  text-align: center;
  color: #777;
  font-size: 26rpx;
}

.desc {
  /* text-indent: 40rpx; */
}
.flex-pc {
  display: flex;
  justify-content: center;
}
.top-title {
  display: flex;
  background-color: #333;
}
.welcome-title {
  flex: 16;
  height: 96rpx;
  line-height: 96rpx;
  text-align: center;
  color: green;
}
.bell-tips {
  flex: 3;
  height: 96rpx;
  line-height: 96rpx;
}
.main-title {
  background-color: #333;
  display: flex;
}
.menu-item {
  flex: 1;
  margin: 10rpx;
}
.main-list {
  /* display: grid;
  grid-template-columns: auto auto auto auto;
  grid-template-rows: auto auto auto; */
  display: flex;
  flex-wrap: wrap;
}
.popup-main-list {
  display: flex;
  flex-wrap: wrap;
  background-color: #fff;
}
.grid-item {
  min-height: 25vw;
  max-height: 25vw;
  max-width: 25vw;
  min-width: 25vw;
  line-height: 25vw;
  text-align: center;
}
.popup-menu-item {
  display: block;
  min-height: 96rpx;
  max-height: 20%;
  max-width: 20%;
  min-width: 20%;
  line-height: 20%;
  text-align: center;
  margin: 2.5%;
}

.grid-item p {
  height: 24rpx;
  line-height: 24rpx;
}
.item-image {
  height: 70%;
  margin: auto auto;
}

.menu-box-popup {
  padding: 10%;
}
.popup-menu-title {
  background-color: #000;
  color: green;
  min-height: 96rpx;
  line-height: 96rpx;
  text-align: center;
}
</style>
