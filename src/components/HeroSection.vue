<template>
  <section id="home" class="hero">
    <div class="hero-bg" />
    <div class="hero-content">
      <img class="avatar" :src="avatarSrc" alt="头像" @error="onError" />
      <h1>Hey，我是 DD</h1>
      <p class="tagline">初二在读 / 编程爱好者 / Minecraft玩家 / 飞友 ✈️</p>
      <p class="bio">一个喜欢写代码、飞机的中学生开发者。用代码构建有趣的东西。</p>
    </div>
    <div class="scroll-hint" @click="scroll">
      <span>看看我做了什么</span>
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <path d="M6 9l6 6 6-6" />
      </svg>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const qq = '3689395508'
const avatarSrc = ref(`https://q1.qlogo.cn/g?b=qq&nk=${qq}&s=640`)

function onError() {
  avatarSrc.value = `data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='96' height='96'%3E%3Crect fill='%23e0e0e0' width='96' height='96'/%3E%3Ctext x='48' y='56' text-anchor='middle' font-size='32' fill='%23aaa'%3ED%3C/text%3E%3C/svg%3E`
}

function scroll() {
  document.getElementById('projects')?.scrollIntoView({ behavior: 'smooth' })
}
</script>

<style scoped>
.hero {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  text-align: center;
  padding: 60px 20px 80px;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background: linear-gradient(170deg, #e8f0fe 0%, #fafafa 40%, #fff0e6 100%);
  z-index: -1;
}

.hero-content {
  position: relative;
  z-index: 1;
}

.avatar {
  width: 96px;
  height: 96px;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid #fff;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  margin-bottom: 24px;
  transition: transform 0.3s;
}

.avatar:hover {
  transform: scale(1.05);
}

h1 {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 8px;
  letter-spacing: -0.5px;
}

.tagline {
  font-size: 1rem;
  color: #777;
  margin-bottom: 16px;
}

.bio {
  max-width: 380px;
  margin: 0 auto;
  font-size: 0.95rem;
  color: #999;
}

.scroll-hint {
  position: absolute;
  bottom: 36px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  cursor: pointer;
  color: #bbb;
  font-size: 0.8rem;
  transition: color 0.2s;
}

.scroll-hint:hover {
  color: #666;
}

.scroll-hint svg {
  animation: bounce 1.8s infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(5px); }
}

@media (max-width: 480px) {
  h1 {
    font-size: 1.6rem;
  }
}
</style>
