<template>
  <div class="container">

    <div>
      <h1 class="title">
        ajcwebdev
      </h1>

      <div class="links">
        <a
          href="https://dev.to/ajcwebdev"
          target="_blank"
          rel="noopener noreferrer"
        >
          Blog
        </a>
        <a
          href="https://github.com/ajcwebdev"
          target="_blank"
          rel="noopener noreferrer"
        >
          GitHub
        </a>
      </div>
    </div>

  </div>
</template>

<style>
  .container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .title {
    font-family:
      'Quicksand',
      'Source Sans Pro',
      -apple-system,
      BlinkMacSystemFont,
      'Segoe UI',
      Roboto,
      'Helvetica Neue',
      Arial,
      sans-serif;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
  }

  .links {
    padding-top: 15px;
  }

  a {
    margin: 10%;
    font-size: 1.5rem;
  }
</style>