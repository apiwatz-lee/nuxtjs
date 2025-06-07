<script setup>
import { menus } from '~/data/menu';

const config = useRuntimeConfig();
const appConfig = useAppConfig();

if (import.meta.server) {
  console.log('server side', config.apiToken);
} else {
  console.log('Client side', config.apiToken);
}
</script>

<template>
  <main class="container mx-auto">
    <nav>
      <ul class="flex gap-10 justify-center p-3 bg-gray-300 relative">
        <li v-for="item in menus" :key="item" class="group">
          <NuxtLink :to="item.link" target="_blank">{{ item.title }} </NuxtLink>

          <!-- Mega Menu -->
          <div
            class="bg-red-200 w-full h-100 absolute left-0 top-12 p-3 opacity-0 invisible transition-all duration-300 group-hover:opacity-100 group-hover:visible"
          >
            <div v-for="subMenu in item.subMenu" :key="subMenu.title">
              <NuxtLink :to="subMenu.link" target="_blank">
                {{ subMenu.title }}
              </NuxtLink>
            </div>
          </div>
        </li>
      </ul>
    </nav>
  </main>
</template>
