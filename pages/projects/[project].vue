<template>
  <main>
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
  </main>
</template>

<script setup>
const route = useRoute()
</script>
