<template>
  <nav
    class="font-sans flex flex-col text-center sm:flex-row sm:text-left sm:justify-between py-4 px-6 bg-white shadow sm:items-baseline w-full"
  >
    <div class="mb-2 sm:mb-0">
      <NuxtLink
        to="/"
        class="text-2xl no-underline text-grey-darkest hover:text-blue-dark"
        >Home</NuxtLink
      >
    </div>
    <div>
      <NuxtLink
        to="/about"
        class="text-lg no-underline text-grey-darkest hover:text-blue-dark ml-2"
        >About</NuxtLink
      >
      <NuxtLink
        to="/_content"
        class="text-lg no-underline text-grey-darkest hover:text-blue-dark ml-2"
        >Content</NuxtLink
      >
    </div>
  </nav>
</template>
