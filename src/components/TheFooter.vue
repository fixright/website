<script setup>
defineProps({
  title: {
    type: String,
    default: 'Default Name',
  },
  subtitle: {
    type: String,
    default: 'Default Subtitle',
  }
})
</script>

<template>
  <footer class="footer">
    <div class="container">
      <div class="col">
        <h4>{{ title }}</h4>
        <p>{{subtitle}}</p>
      </div>
      <div class="col links">
        <h4>Legal</h4>
        <ul>
          <li><a href="/privacypolicy">Privacy Policy</a></li>
          <li><a href="/teamsofservice">Terms of Service</a></li>
          <li><a href="cookiepolicy">Cookie Policy</a></li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: var(--color-dark);
  color: white;
  padding: 20px;
}

.container {
  max-width: var(--max-width);
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}

h4 { margin-bottom: 0.5rem; color: white; }
p { color: #8fa6c9; max-width: 300px; }

.links ul { list-style: none; }
.links a {
  color: #8fa6c9;
  text-decoration: none;
  display: block;
  margin-bottom: 0.3rem;
}
.links a:hover { color: white; }

@media (max-width: 600px) {
  .container { flex-direction: column; gap: 2rem; }
}
</style>