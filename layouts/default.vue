<template>
  <div>
    <header class="menu">
      <nav>
        <ul>
          <li><nuxt-link to="/">Home</nuxt-link></li>
          <li><nuxt-link to="/plants">Plants</nuxt-link></li>
        </ul>
      </nav>
    </header>
    <main>
      <NuxtPage />
    </main>
  </div>
</template>

<style scoped>
.menu {
  background: #2c3e50;
  padding: 10px;
}

.menu nav ul {
  display: flex;
  list-style: none;
  justify-content: center;
  gap: 20px;
  margin: 0;
  padding: 0;
}

.menu nav ul li a {
  text-decoration: none;
  color: #fff;
  font-size: 18px;
  font-weight: bold;
}

.menu nav ul li a:hover {
  text-decoration: underline;
}
</style>