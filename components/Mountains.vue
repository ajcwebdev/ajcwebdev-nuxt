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