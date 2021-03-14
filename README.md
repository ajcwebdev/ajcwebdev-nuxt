# a first look at nuxtJS: part 1 - setup, pages

NuxtJS is a Vue meta-framework created by [Sébastien Chopin in October 2016](https://github.com/nuxt/nuxt.js/commit/0072ed31da6ce39d21046e05898f956cff190390). It is a progressive framework designed for creating modern web applications. It is based on official Vue libraries including Vue Core, Vue Router, and Vuex.

## Start development server

```bash
yarn
yarn dev
```

Open up `localhost:3000` in a browser.

### Configuration

Our `nuxt.config.js` file contains `target` set to `static` for deployment.

```javascript
// nuxt.config.js

export default {
  target: 'static'
}
```

Our `netlify.toml` file sets the publish directory to `dist` and the build command to `nuxt generate`.

```toml
[build]
  publish = "dist/"
  command = "nuxt generate"
```

### Home page

The home page include an `<h1>` for the title of the page and links to some of your social media accounts.

```html
// pages/index.vue

<template>
  <div class="container">
    <header>
      <h1>ajcwebdev</h1>
    </header>

    <p>This is the home page</p>

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

![03-home-page-with-css](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gwfbu5emfia1nf6hinxn.png)

### About page

The component includes an `<h1>` tag for the title and a `<p>` tag containing a brief description of the page.

```html
// pages/about.vue

<template>
  <div class="container">
    <p>This page tells you about stuff</p>
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

![05-about-page-with-css](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cmuyi1ca27b450pa0c7r.png)
