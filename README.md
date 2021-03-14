# a first look at nuxtJS - part 1

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
```

![03-](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ky4kczhxfn2blcoe1su8.png)

### About page

The component includes an `<h1>` tag for the title and a `<p>` tag containing a brief description of the page.

```html
// pages/about.vue

<template>
  <div class="container">

    <div>
      <h1 class="title">
        About
      </h1>

      <p class="body">
        This page tells you about stuff
      </p>
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

  .body {
    font-size: 1.5rem;
  }
</style>
```

![05-](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/6zrtpyb0rikfibss4l5z.png)