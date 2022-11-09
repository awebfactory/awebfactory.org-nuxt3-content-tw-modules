<template>
  <main>
    <ContentQuery :path="$route.path" find="one" v-slot="{ data }">
      <ContentRenderer :value="data">
        <h2>{{ data.title }}</h2>
        <h3>{{ data.description }}</h3>
        <div>
          <p>Start date: {{ data.startDate }}</p>
          <p>End date: {{ data.endDate }}</p>
          <p>MVP: {{ data.mvp }}</p>
          <p>Status: {{ data.status }}</p>
        </div>
        <p class="text-green-500">excerpt:</p>
        <ContentRendererMarkdown class="prose" :value="data" excerpt />
        <p class="text-green-500">full text:</p>
        <ContentRendererMarkdown class="prose" :value="data" />
      </ContentRenderer>
    </ContentQuery>
  </main>
</template>

<script setup>
const route = useRoute()
</script>
