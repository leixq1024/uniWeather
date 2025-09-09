<!-- 启动页 -->
<template>
  <div class="startup">
    <img src="/static/images/startupLogo.png" alt="logo" class="logo" />
    <!-- 文字描述 -->
    <div class="info">
      <div class="title">天气</div>
      <div class="sub-title">预报</div>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.startup {
  position: relative;
  width: 100vw;
  height: 100vh;
  background: linear-gradient(226.41deg, rgba(242, 244, 247, 1) 0%, rgba(188, 200, 214, 1) 100%);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 24px;
  .logo {
    width: 200px;
    height: 147px;
  }
  .info {
    .title {
      font-size: 40px;
      font-weight: 600;
      letter-spacing: 3px;
      line-height: 50px;
      color: rgba(10, 10, 34, 1);
    }
    .sub-title {
      font-size: 24px;
      font-weight: 400;
      letter-spacing: 3px;
      line-height: 50px;
      color: rgba(139, 149, 162, 1);
      text-align: center;
      vertical-align: top;
    }
  }
}
</style>
