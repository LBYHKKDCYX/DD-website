<template>
  <div class="card">
    <img class="card-icon" :src="project.icon" :alt="project.name + ' logo'" />
    <h3 v-text="project.name" />
    <p class="card-desc" v-text="project.desc" />
    <div class="card-tags">
      <span v-for="t in project.tags" :key="t" v-text="t" />
    </div>
    <div class="card-links">
      <a v-if="project.url" :href="project.url" target="_blank" rel="noopener">🔗 官网</a>
      <span v-if="project.qq" class="qq" v-text="'🐧 ' + project.qq" />
    </div>
  </div>
</template>

<script setup>
defineProps({
  project: { type: Object, required: true },
})
</script>

<style scoped>
.card {
  background: #fff;
  border: 1px solid #eee;
  border-radius: 12px;
  padding: 24px;
  transition: box-shadow 0.25s, transform 0.25s;
}

.card:hover {
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.06);
  transform: translateY(-2px);
}

.card-icon {
  width: 40px;
  height: 40px;
  object-fit: contain;
  margin-bottom: 12px;
}

h3 {
  font-size: 1.05rem;
  font-weight: 600;
  margin-bottom: 8px;
}

.card-desc {
  font-size: 0.9rem;
  color: #777;
  margin-bottom: 14px;
  line-height: 1.6;
}

.card-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-bottom: 14px;
}

.card-tags span {
  font-size: 0.75rem;
  padding: 2px 10px;
  background: #f0f0f0;
  border-radius: 20px;
  color: #666;
}

.card-links {
  display: flex;
  gap: 16px;
  font-size: 0.88rem;
  align-items: center;
}

.card-links a {
  color: #3367d6;
  font-weight: 500;
  transition: opacity 0.2s;
}

.card-links a:hover {
  opacity: 0.7;
}

.qq {
  color: #999;
  font-size: 0.82rem;
}
</style>
