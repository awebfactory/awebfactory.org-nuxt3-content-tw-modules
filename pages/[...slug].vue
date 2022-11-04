<template>
  <main>
    <ContentDoc>
      <template #not-found>        
        <div class="p-4 mx-auto max-w-screen-md">
        <p>
          Hi there! Did you mean project{{" "}}{{ route. params.slug }}?
          <span class="text-green-400">
            <p>no doc</p>
          </span>
        </p>
        <p>
          Sorry, we can't find any project with that name. But, click to see a{{" "}}
          <a href="project" class="bg-yellow-100 hover:bg-yellow-200">
            recent project
          </a>
        </p>
      </div>
      </template>
    </ContentDoc>
  </main>
</template>

<script setup>
  const route = useRoute()
  // console.log('hola', route.params) 
</script>