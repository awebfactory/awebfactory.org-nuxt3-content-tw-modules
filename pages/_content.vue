<template>
  <main>
    <h2 class="text-awf-dark-brown">Content Model</h2>
    <pre>{{ data }}</pre>
  </main>
</template>

<script setup>
const { data } = await useAsyncData(() => {
  // return queryContent().findOne()
  const theContent = queryContent().find()
  return theContent
})
// console.log(data)
</script>
