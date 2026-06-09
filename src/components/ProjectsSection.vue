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
    name: '飞行助手',
    desc: '一个ICAO 机场代码查询 & METAR 气象报文实时查询和翻译的小工具，基于 Flask + Vue 3 构建',
    tags: ['METAR', 'ICAO', 'Vue', 'Python', 'Flask'],
    url: 'https://github.com/LBYHKKDCYX/Flight-Assistant',
  },
  {
    name: '图形化网页开发工具',
    desc: '一款运行在浏览器中的图形化 Web 开发 IDE，支持 HTML、CSS、JavaScript 等前端技术的开发。',
    tags: ['Web', '开发', 'CSS', 'JavaScript', 'Vue', 'TypeScript'],
    url: 'https://github.com/LBYHKKDCYX/Graphical-Web-Development-Tools.git',
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
