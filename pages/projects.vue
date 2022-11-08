<template>
  <main>
    <header>
      <h2>Projects</h2>
    </header>
    <ul v-if="equalQuery">
      <li v-for="project in equalQuery" :key="project.slug">
        {{ project.title }}
      </li>
    </ul>
  </main>
</template>

<script setup>
const { data: equalQuery } = await useAsyncData("equal", () => {
  return queryContent("/projects").where({ type: "project" }).find()
})

// console.log(equalQuery)
</script>
