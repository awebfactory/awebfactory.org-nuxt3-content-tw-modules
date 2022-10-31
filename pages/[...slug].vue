<script setup>
const { path } = useRoute()
const { data } = await useAsyncData(`content-${path}`, () => {
  return queryContent().where({ _path: path }).only(["title"]).findOne()
})
</script>

<template>
  <main>
    <h2 class="text-awf-dark-brown">AWF org</h2>
    <h3 class="text-awf-bright-orange">here</h3>
    <p class="text-xs text-awf-dark-brown">here2</p>
    <p class="text-awf-dark-green font-bold">here3</p>
    <p class="text-awf-dark-orange font-extrabold">here4</p>
    <ContentDoc />
    <pre>{{ data.title }}</pre>
  </main>
</template>
