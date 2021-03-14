# a first look at nuxtJS: part 2 - layout, components, data fetching

## Start development server

```bash
yarn
yarn dev
```

Open up `localhost:3000` in a browser.

### Configuration

Set `components` to `true` in `nuxt.config.js`

```javascript
// nuxt.config.js

export default {
  target: 'static',
  components: true
}
```

### Layout

```html
// layouts/default.vue

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
```

### Mountains component

```html
// components/Mountains.vue

<template>
  <div class="container">
    <h2>Mountains</h2>

    <p v-if="$fetchState.pending">
      Almost there...
    </p>

    <p v-else-if="$fetchState.error">
      Error
    </p>

    <div v-else>
      <ul>
        <li
            v-for="mountain of mountains"
            v-bind:key="mountain.items"
          >
          {{ mountain.title }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        mountains: []
      }
    },
    async fetch() {
      this.mountains = await fetch(
        'https://api.nuxtjs.dev/mountains'
      )
      .then(res => res.json())
      console.log(this.mountains)
    }
  }
</script>
```

### Home page

```html
// pages/index.vue

<template>
  <div class="container">
    <p>This is the home page</p>
    <Mountains />
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
```

![05-](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/x56kcexozzt37ohbbry7.png)
