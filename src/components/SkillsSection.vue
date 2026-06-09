<template>
  <section id="skills" class="section-alt">
    <h2 class="section-title">技术栈</h2>
    <div class="cloud">
      <span v-for="s in skills" :key="s" class="tag" v-text="s" />
    </div>
  </section>
</template>

<script setup>
const skills = [
  'Vue.js', 'JavaScript', 'HTML & CSS', 'Git', 'Python'
]
</script>

<style scoped>
.cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.tag {
  font-size: 0.88rem;
  padding: 6px 18px;
  background: #fff;
  border: 1px solid #e0e0e0;
  border-radius: 20px;
  color: #444;
  transition: border-color 0.2s;
}

.tag:hover {
  border-color: #f0a040;
}
</style>
