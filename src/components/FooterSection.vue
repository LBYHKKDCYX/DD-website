<template>
  <footer class="footer">
    <p>&copy; {{ year }} DD</p>
    <p class="qq">QQ：3689395508</p>
    <div class="links">
      <a href="https://qm.qq.com/cgi-bin/qm/qr?k=36893955508" target="_blank" rel="noopener">联系我</a>
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>

<style scoped>
.footer {
  text-align: center;
  padding: 40px 20px;
  color: #aaa;
  font-size: 0.82rem;
  border-top: 1px solid #eee;
}

.qq {
  margin: 4px 0;
}

.links {
  margin-top: 10px;
}

.links a {
  color: #888;
  transition: color 0.2s;
}

.links a:hover {
  color: #3367d6;
}
</style>
