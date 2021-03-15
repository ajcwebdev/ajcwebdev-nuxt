<template>
  <div class="container">
    <header>
      <h1>ajcwebdev</h1>

      <nav>
        <ul>
          <li>
            <NuxtLink to="/">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about">About</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/jokes">Jokes</NuxtLink>
          </li>
        </ul>
      </nav>
    </header>

    <main>
      <Nuxt />
    </main>

    <footer>
      <a
        href="https://dev.to/ajcwebdev"
        target="_blank"
      >
        Blog
      </a>
      <a
        href="https://github.com/ajcwebdev"
        target="_blank"
      >
        GitHub
      </a>
    </footer>
  </div>
</template>

<style>
  .container {
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
</style>