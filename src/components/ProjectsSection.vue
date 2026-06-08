<template>
  <section id="projects" class="section">
    <h2 class="section-title">项目</h2>
    <div class="grid">
      <ProjectCard v-for="p in projects" :key="p.name" :project="p" />
    </div>
  </section>
</template>

<script setup>
import ProjectCard from './ProjectCard.vue'

const projects = [
  {
    name: 'ISFP 云际模拟飞行连飞平台',
    desc: 'Interstellar Simulation Flight Platform，为模拟飞行爱好者打造的线上连飞平台，连接全球飞友一同翱翔蓝天。',
    icon: import.meta.env.BASE_URL + 'logos/isfp.png',
    tags: ['模拟飞行', '连飞平台', 'Vue'],
    url: 'https://www.flyisfp.com',
    qq: 'QQ群 644614465',
  },
  {
    name: 'QuanQuan Network',
    desc: '一个Minecraft小游戏服务器，为玩家提供轻松有趣的多人游戏体验，和小伙伴们一起快乐玩耍。',
    icon: import.meta.env.BASE_URL + 'logos/quanquan-network.png',
    tags: ['Minecraft', '小游戏', '服务器'],
    url: 'https://mc.flyisfp.com',
    qq: 'QQ群 435624385',
  },
]
</script>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}
</style>
