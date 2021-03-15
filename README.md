# a first look at nuxtJS: part 3 - route parameters, dynamic pages

## Start development server

```bash
yarn
yarn dev
```

Open up `localhost:3000` in a browser.

### Configuration

Add `@nuxtjs/axios` to `modules` in config file

```javascript
// nuxt.config.js

export default {
  target: 'static',
  components: true,
  modules: [
    '@nuxtjs/axios',
  ]
}
```

### Joke component

```html
// components/Joke.vue

<template>
  <NuxtLink :to="'jokes/' + id">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </NuxtLink>
</template>

<script>
export default {
  name: "Joke",
  props: [
    "joke",
    "id"
  ]
}
</script>

<style>
.joke {
  padding: .75rem;
  border: 1px solid black;
  border-radius: .5rem;
  margin: .75rem 0;
  font-size: 1.25rem;
}
</style>
```

### Jokes page

```html
// pages/Jokes/index.vue

<template>
  <div>
    <h2>Jokes</h2>

    <Joke
      v-for="joke in jokes"
      :key="joke.id"
      :id="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>

<script>
import axios from "axios"

export default {
  data() {
    return {
      jokes: []
    }
  },

  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    }

    try {
      const res = await axios.get(
        "https://icanhazdadjoke.com/search",
        config
      )

      this.jokes = res.data.results
      console.log(this.jokes)
    } catch (err) {
      console.log(err)
    }
  }
}
</script>
```

![05-link-to-dynamic-page](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/j9be0jc04oe8zc4fgfb7.png)

### Dynamic pages

```html
// pages/Jokes/_id/index.vue

<template>
  <div>
    <NuxtLink to="/jokes">
      Back To Jokes
    </NuxtLink>
    
    <h2>
      {{ joke }}
    </h2>

    <small>
      ID: {{ $route.params.id }}
    </small>
  </div>
</template>

<script>
import axios from "axios"

export default {
  data() {
    return {
      joke: {}
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    }

    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      )

      this.joke = res.data.joke
    } catch (err) {
      console.log(err)
    }
  }
}
</script>
```

![04-dynamic-page](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bgko6u6r77kj4txkurvy.png)