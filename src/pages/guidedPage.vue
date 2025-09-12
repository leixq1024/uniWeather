<!-- 引导页 -->
<template>
  <div class="guide">
    <!-- 跳过按钮 -->
    <div class="skip">跳过</div>
    <div class="logo-box">
      <up-swiper
        class="logo"
        :list="infoList"
        :indicator="true"
        indicatorMode="dot"
        indicatorActiveColor="#0A0A22"
        indicatorInactiveColor="#fff"
        @change="onSwiperChange"
      >
        <template v-slot:default="{ item }">
          <img class="logo" :src="item['img']" alt="logo" />
        </template>
      </up-swiper>
    </div>
    <div class="info-box">
      <div class="title">{{ infoList[currentIndex]['title'] }}</div>
      <div class="sub-title">{{ infoList[currentIndex]['subTitle'] }}</div>
      <!-- 下一步按钮 -->
      <div class="next-btn__wapper" :style="styleVar">
        <div class="next-btn"></div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import 夜晚 from '@/static/images/夜晚.png'
import 晴天 from '@/static/images/晴天.png'
import 雨天 from '@/static/images/雨天.png'
import 晴多云 from '@/static/images/晴-多云.png'
const currentIndex = ref(0)
const infoList = ref([
  {
    img: 夜晚,
    title: '详细的小时天气预报',
    subTitle: '提供未来24小时精确到每小时的天气变化，包括温度、降水概率和风速，帮助您规划每一天。'
  },
  {
    img: 晴天,
    title: '实时天气雷达图',
    subTitle: '通过高清雷达图实时追踪降水、雪和风暴，让您随时了解天气动态，提前做好准备。'
  },
  {
    img: 雨天,
    title: '全球城市天气',
    subTitle: '添加并管理多个城市，轻松滑动切换，随时掌握全球各地的天气情况，出行无忧。'
  },
  {
    img: 晴多云,
    title: '个性化天气提醒',
    subTitle: '自定义天气预警通知，包括温度骤变、降水提醒等，确保您永远不会被天气突袭。'
  }
])
const styleVar = ref({ '--progress': '75%' })
// 轮播图切换事件
const onSwiperChange = data => {
  currentIndex.value = data['current']
  if (currentIndex.value === 3) {
    styleVar.value = {
      '--progress': '100'
    }
  } else {
    styleVar.value = {
      '--progress': (3 - currentIndex.value) * 25 + '%'
    }
  }
}
</script>

<style lang="scss" scoped>
::v-deep .logo-box {
  position: relative;
  width: 100%;
  height: 300px;
  box-sizing: border-box;
  display: flex;
  align-items: center;
  justify-items: center;
  .u-swiper {
    width: 100% !important;
    height: 380px !important;
    background: none !important;
    .u-swiper__wrapper__item {
      display: flex;
      align-items: flex-end;
      justify-content: center;
      box-sizing: border-box;
      padding-bottom: 48px;
      .logo {
        width: 200px;
        height: 200px;
        transform: scale(1.8);
      }
    }
    .u-swiper__wrapper {
      height: 100% !important;
    }
  }
}
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
  padding: 48px 120px 80px 120px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.title {
  font-size: 26px;
  font-weight: 600;
  letter-spacing: 2px;
  line-height: 33px;
  color: rgba(10, 10, 34, 1);
  text-align: center;
  vertical-align: top;
}
.sub-title {
  margin-top: 21px;
  font-size: 14px;
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
  top: 24px;
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
.next-btn {
  position: absolute;
  width: 82px;
  height: 82px;
  border-radius: 50%;
  background: #fff url('@/static/images/nextBtn.png') no-repeat;
  background-position: center;
  z-index: 2;
  &__wapper {
    position: relative;
    margin-top: 24px;
    background: #bbc5d4;
    width: 86px;
    height: 86px;
    display: flex;
    border-radius: 50%;
    pointer-events: none;
    display: flex;
    align-items: center;
    justify-content: center;
    &::before {
      position: absolute;
      content: '';
      width: 90px;
      height: 90px;
      background: linear-gradient(240deg, rgba(255, 79, 128, 1) 0%, rgba(194, 58, 204, 1) 100%) 0;
      border-radius: 50%;
      z-index: 0;
      display: block;
    }
    &::after {
      position: absolute;
      content: '';
      width: 90px;
      height: 90px;
      background: conic-gradient(#bbc5d4 var(--progress), transparent);
      border-radius: 50%;
      z-index: 1;
      display: block;
    }
  }
}
</style>
