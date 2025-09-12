<!-- 引导页 -->
<template>
  <div class="guide">
    <!-- 跳过按钮 -->
    <div class="skip">跳过</div>
    <img class="logo" :src="infoList[activeIndex]['img']" alt="logo" />
    <div class="info-box">
      <div class="title">{{ infoList[activeIndex]['title'] }}</div>
      <div class="sub-title">{{ infoList[activeIndex]['subTitle'] }}</div>
      <!-- 下一步按钮 -->
      <div class="next-btn"></div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import 夜晚 from '@/static/images/夜晚.png'
import 晴天 from '@/static/images/晴天.png'
import 雨天 from '@/static/images/雨天.png'
import 晴多云 from '@/static/images/晴-多云.png'
const activeIndex = ref(0)
const infoList = ref([
  {
    img: 夜晚,
    title: '详细的小时预报',
    subTitle: '获取深入的天气信息。'
  },
  {
    img: 晴天,
    title: '实时天气图',
    subTitle: '查看降水进展以保持知情'
  },
  {
    img: 雨天,
    title: '世界各地的天气',
    subTitle: '添加任何你想要的位置，轻松滑动即可更改。'
  },
  {
    img: 晴多云,
    title: '详细的小时预报',
    subTitle: '获取深入的天气信息。'
  }
])
</script>

<style lang="scss" scoped>
.guide {
  position: relative;
  width: 360px;
  height: 760px;
  background: linear-gradient(180deg, rgba(72, 75, 91, 1) 0%, rgba(44, 45, 53, 1) 100%);
}
.info-box {
  position: absolute;
  left: -66px;
  top: 363px;
  width: 493px;
  height: 493px;
  background: #fff;
  border-radius: 50%;
  padding: 81px 120px;
  box-sizing: border-box;
}
.logo {
  width: 370px;
  height: 370px;
}
.title {
  font-size: 28px;
  font-weight: 600;
  letter-spacing: 2px;
  line-height: 33px;
  color: rgba(10, 10, 34, 1);
  text-align: center;
  vertical-align: top;
}
.sub-title {
  margin-top: 21px;
  font-size: 16px;
  font-weight: 400;
  letter-spacing: 2px;
  line-height: 22px;
  color: rgba(139, 149, 162, 1);
  text-align: center;
  vertical-align: top;
}
.skip {
  position: absolute;
  left: 299px;
  top: 43px;
  width: 32px;
  height: 20px;
  font-size: 14px;
  font-weight: 500;
  letter-spacing: 0px;
  line-height: 20px;
  color: rgba(255, 255, 255, 1);
  text-align: right;
  vertical-align: top;
}
.next-btn {
  width: 64px;
  height: 64px;
  border-radius: 50%;
}
</style>
