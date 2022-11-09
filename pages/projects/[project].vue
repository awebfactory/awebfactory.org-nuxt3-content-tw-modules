<template>
  <main>
    <h1>Two ways to do things (pedagogical mess!)</h1>
    <ContentQuery :path="$route.path" v-slot="{ data }">
      <h2>{{ data[0].title }}</h2>
      <h3>{{ data[0].description }}</h3>
      <div>
        <p>Start date: {{ data[0].startDate }}</p>
        <p>End date: {{ data[0].endDate }}</p>
      </div>
      <details>
        <summary>Click for detailed project data</summary>
        <pre>{{ data[0] }}</pre>
        <ContentRenderer :value="data[0].excerpt" />
      </details>
    </ContentQuery>
    <ContentDoc />
    <hr />
    <hr />
    <hr />
    <hr />
    <ContentRenderer :value="data">
      <h2>{{ data.title }}</h2>
      <h3>{{ data.description }}</h3>
      <div>
        <p>Start date: {{ data.startDate }}</p>
        <p>End date: {{ data.endDate }}</p>
      </div>
      <!-- Content Query + ContentRendererMarkdown is the same as ContentDoc -->
      <ContentRendererMarkdown :value="data" />
      <ContentDoc />
    </ContentRenderer>
  </main>
</template>

<script setup>
const route = useRoute()
const { data } = await useAsyncData("page-data", () =>
  queryContent(route.path).findOne()
)
</script>
