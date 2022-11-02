<script setup>
import {
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
  Menu,
  MenuButton,
  MenuItem,
  MenuItems,
} from "@headlessui/vue"
import { Bars3Icon, XMarkIcon } from "@heroicons/vue/24/outline/index.js"

const navigation = [
  { name: "Projects", to: "/projects" },
  { name: "Process", to: "/process" },
  { name: "Resources", to: "/resources" },
  { name: "About", to: "/about" },
]
</script>
<template>
  <Disclosure as="nav" class="bg-texas-rose-50" v-slot="{ open }">
    <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
      <div class="relative flex h-16 items-center justify-between">
        <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
          <!-- Mobile menu button-->
          <DisclosureButton
            class="inline-flex items-center justify-center rounded-md p-2 text-awf-dark-orange hover:bg-awf-dark-orange hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
          >
            <span class="sr-only">Open main menu</span>
            <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
            <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
        <div
          class="flex flex-1 items-center justify-center sm:items-stretch sm:justify-start"
        >
          <div class="flex flex-shrink-0 items-center">
            <NuxtLink to="/">
              <img
                class="block h-12 w-auto lg:hidden"
                src="/logo.png"
                alt="Your Company"
              />
              <img
                class="hidden h-12 w-auto lg:block"
                src="/logo.png"
                alt="Your Company"
              />
            </NuxtLink>
          </div>
          <div class="hidden sm:mx-auto sm:mt-2 sm:block">
            <div class="flex space-x-4 justify-end">
              <NuxtLink
                v-for="item in navigation"
                :key="item.name"
                :to="item.to"
                :class="[
                  item.active
                    ? 'bg-gray-900 text-white'
                    : 'text-awf-dark-orange hover:bg-awf-dark-orange hover:text-white',
                  'px-3 py-2 rounded-md text-sm font-medium',
                ]"
                :aria-active="item.active ? 'page' : undefined"
                >{{ item.name }}</NuxtLink
              >
            </div>
          </div>
        </div>
      </div>
    </div>

    <DisclosurePanel class="sm:hidden">
      <div class="space-y-1 px-2 pt-2 pb-3">
        <DisclosureButton
          v-for="item in navigation"
          :key="item.name"
          as="a"
          :to="item.to"
          :class="[
            item.active
              ? 'bg-gray-900 text-white'
              : 'text-awf-dark-orange hover:bg-awf-dark-orange hover:text-white',
            'block px-3 py-2 rounded-md text-base font-medium',
          ]"
          :aria-active="item.router - link - active ? 'page' : undefined"
          >{{ item.name }}</DisclosureButton
        >
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

<style>
a {
  color: #996633;
  background-color: transparent;
}
a.router-link-active {
  color: white;
  background-color: #996633;
}
a img {
  color: #f0e8d1;
  background-color: #fff8eb;
}
a.router-link-active img {
  color: white;
  background-color: #f0e8d1;
  padding: 2px;
}
</style>
