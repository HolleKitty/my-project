<template>
  <view class="TabBar">
    <view
      class="tab"
      v-for="(item, index) in TabBarList"
      :key="index"
      @tap="navigatorTo(item.url)"
    >
      <!-- 判断是否有点击，若是没有就不是激活样式，点击就是激活的样式 -->
      <image
        class="imgsize"
        v-if="item.type == 0"
        :src="current == index ? item.selectIcon : item.icon"
        mode="widthFix"
      ></image>
      <!-- 设置一个状态值（type），判断加号是否展现 -->
      <image
        class="addimgsize"
        v-if="item.type == 1"
        src="../static/c1.png"
        mode="widthFix"
      ></image>
      <view class="text">{{ item.name }}</view>
    </view>
  </view>
</template>

<script>
export default {
  props: {
    current: {
      type: Number,
      default: 0, //默认第一个页面tabbar激活
    },
  },
  data() {
    return {
      TabBarList: [
        {
          type: 0,
          icon: "../../static/record.png",
          selectIcon: "../../static/template.png",
          name: "工作",
          url: "../index/index",
        },
        {
          type: 0,
          icon: "../../static/component.png",
          selectIcon: "../../static/component.png",
          name: "助手",
          url: "#",
        },
        {
          type: 1,
          icon: "../../static/menu.png",
          selectIcon: "../../static/template.png",
          name: "常用",
          url: "#",
        },
        {
          type: 0,
          icon: "../../static/template.png",
          selectIcon: "../../static/menu.png",
          name: "分析",
          url: "#",
        },
        {
          type: 0,
          icon: "../../static/plus.png",
          selectIcon: "../../static/template.png",
          name: "我",
          url: "#",
        },
      ],
    };
  },
  methods: {
    navigatorTo(e) {
      uni.redirectTo({
        url: e,
      });
    },
  },
};
</script>

<style scoped>
.TabBar {
  position: fixed;
  bottom: 0;
  height: 80upx;
  background-color: #fff;
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.tab {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.imgsize {
  width: 40upx;
  height: 40upx;
}
.addimgsize {
  width: 70upx;
  height: 70upx;
  margin-top: -30upx;
}
.text {
  font-size: 12px;
}
</style>
