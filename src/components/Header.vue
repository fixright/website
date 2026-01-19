<script setup>

</script>

<template>
  <section class="header">
    <div class="logo">
      <h3 style="color: var(--color-primary)">Fix</h3>
      <h3 style="color: white">Right</h3>
    </div>

    <div class="navigation">
      <a href="#gallery">Gallery</a>
      <a href="#location">Location</a>
      <a href="#services">Services</a>
      <a href="#reviews">Reviews</a>
      <a href="#contact">Contacts</a>
    </div>
  </section>
</template>

<style scoped>
.header {
  justify-content: space-around;
  align-items: center;
  display: flex;
  flex-direction: row;
  height: 60px;
  width: 100%;
  background-color: var(--color-dark);
}

.header .logo {
  display: flex;
  flex-direction: row;
}

.header .logo h3 {
  position: relative;
  bottom: -0.2em;
}

.header .navigation {
  display: flex;
  flex-direction: row;
  gap: 10px;
}

.header .navigation a {
  text-decoration: none;
  color: white;
  opacity: 0.7;
}

.header .navigation a:hover {
  text-decoration: none;
  color: white;
  opacity: 0.9;
}

@media (max-width: 500px) {
  .header .navigation
  {
    display: none;
  }

  .header
  {
    display: flex;
    justify-content: normal;
  }

  .logo{
    margin-left: 50px;
  }
}
</style>