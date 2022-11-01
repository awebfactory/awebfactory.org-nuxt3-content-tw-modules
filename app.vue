<script setup>
useHead({
  htmlAttrs: {
    lang: "en",
  },
  charset: "utf-8",
  title: "Project Flow & Tracker",
  titleTemplate: (title) =>
    title !== "Project Flow & Tracker"
      ? `${title} · Project Flow & Tracker`
      : title,
  meta: [{ name: "description", content: "build in public, learn in public" }],
  link: [
    {
      rel: "icon",
      type: "image/ico",
      href: "/favicon.ico",
    },
  ],
})
</script>

<template>
  <NuxtLayout>
    <div
      class="prose bg-texas-rose-100 p-12 w-full h-full min-h-screen flex flex-col items-center"
    >
      <NuxtPage />
    </div>
  </NuxtLayout>
</template>
