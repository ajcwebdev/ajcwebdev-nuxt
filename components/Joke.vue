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