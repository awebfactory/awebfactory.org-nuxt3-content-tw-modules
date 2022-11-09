<template>
  <main>
    <ContentRenderer :value="data">
      <h2>{{ data.title }}</h2>
      <h3>{{ data.description }}</h3>
      <div>
        <p>Start date: {{ data.startDate }}</p>
        <p>End date: {{ data.endDate }}</p>
        <p>MVP: {{ data.mvp }}</p>
        <p>Status: {{ data.status }}</p>
      </div>
      <ContentRendererMarkdown :value="data" />
    </ContentRenderer>
  </main>
</template>

<script setup>
const route = useRoute()
const { data } = await useAsyncData("page-data", () =>
  queryContent(route.path).findOne()
)
</script>
