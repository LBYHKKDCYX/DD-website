<template>
  <nav class="nav" :class="{ scrolled }">
    <span class="nav-brand">QuanQuan</span>
    <div class="nav-links">
      <a v-for="item in items" :key="item.id" :href="'#' + item.id" v-text="item.label" />
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const scrolled = ref(false)
const items = [
  { id: 'home', label: '首页' },
  { id: 'projects', label: '项目' },
  { id: 'skills', label: '技能' },
  { id: 'about', label: '关于' },
]

function onScroll() {
  scrolled.value = window.scrollY > 40
}

onMounted(() => window.addEventListener('scroll', onScroll, { passive: true }))
onBeforeUnmount(() => window.removeEventListener('scroll', onScroll))
</script>

<style scoped>
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 28px;
  height: 56px;
  transition: background 0.25s, box-shadow 0.25s;
}

.nav.scrolled {
  background: rgba(255, 255, 255, 0.85);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  box-shadow: 0 1px 0 rgba(0, 0, 0, 0.06);
}

.nav-brand {
  font-weight: 700;
  font-size: 1.1rem;
  letter-spacing: -0.3px;
}

.nav-links {
  display: flex;
  gap: 22px;
}

.nav-links a {
  font-size: 0.9rem;
  color: #555;
  transition: color 0.2s;
}

.nav-links a:hover {
  color: #000;
}

@media (max-width: 480px) {
  .nav {
    padding: 0 16px;
  }
  .nav-links {
    gap: 14px;
  }
}
</style>
