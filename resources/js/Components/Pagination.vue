<script setup>
  import { Link } from '@inertiajs/vue3';

  defineProps({
    links: Array
  });
</script>

<template>
  <div v-if="links.length > 3">
    <div class="flex flex-wrap -mb-1">
      <template v-for="(link, p) in links" :key="p">
        <Link
          v-if="link.url"
          class="mr-1 px-4 py-2 text-sm border rounded-md hover:bg-gray-100"
          :class="{ 'bg-teal-700 text-white hover:bg-teal-800': link.active }"
          :href="link.url"
          v-html="link.label"
        />

        <div
          v-else
          class="mr-1 px-4 py-2 text-sm text-gray-400 border rounded-md"
          v-html="link.label"
        />
      </template>
    </div>
  </div>
</template>
