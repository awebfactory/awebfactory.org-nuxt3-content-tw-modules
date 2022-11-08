<template>
  <main>
    <header>
      <h2>Project Flow & Tracker</h2>
      <p class="text-awf-dark-green">
        No topic to be isolated, everything must offer value, be done for a
        purpose, project-based, inserted in its own history, ready to be re-used
        or pivoted.
      </p>
      <div className="mx-auto mt-3 max-w-2xl text-sm text-slate-500 sm:mt-4">
        <ul>
          <li>
            <strong>Case Studies</strong>: An overview, emphasizing what makes
            each project especially useful
          </li>
          <li>
            <strong>Process</strong>: The lean and agile artifacts of project
            history through all iterations to date useful
          </li>
          <li>
            <strong>Resources</strong>: Projects with real value #BuiltInPublic
            so we can #LearnInPublic
          </li>
          <li>
            <strong>Online dev</strong>: Open Source Repos with no vendor
            lock-in running on online dev environments️
          </li>
        </ul>
      </div>
    </header>
    <div
      v-if="equalQuery"
      className="mx-auto mt-8 grid max-w-lg gap-5 sm:grid-cols-2 lg:max-w-none lg:grid-cols-3"
    >
      <div
        v-for="project in equalQuery"
        :key="project.slug"
        className="flex flex-col overflow-hidden rounded-lg shadow-lg"
      >
        <div className="flex flex-1 flex-col justify-between bg-white p-6">
          <div class="flex-1">
            <NuxtLink :to="`/projects/${project.slug}`" className="mt-2 block">
              <p
                className="text-xl font-semibold text-orange-peel-800 hover:text-wild-willow-400"
              >
                {{ project.title }}
              </p>
              <p className="mt-3 text-base text-gray-500">
                {{ project.description }}
              </p>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
const { data: equalQuery } = await useAsyncData("equal", () => {
  return queryContent("/projects").where({ type: "project" }).find()
})

// console.log(equalQuery)
</script>
