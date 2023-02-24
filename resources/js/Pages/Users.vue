<script setup>
import Pagination from '@/Components/Pagination.vue';

defineProps({
  users: Object,
});
</script>

<template>
  <div class="p-10">
    <div class="border rounded-md mb-6">
      <table class="w-full">
        <thead>
          <tr>
            <th class="bg-gray-100 text-left p-3">ID</th>
            <th class="bg-gray-100 text-left p-3">Name</th>
            <th class="bg-gray-100 text-left p-3">Email</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="user in users.data" :key="user.id">
            <td class="border-t p-3">{{ user.id }}</td>
            <td class="border-t p-3">{{ user.name }}</td>
            <td class="border-t p-3">{{ user.email }}</td>
          </tr>
        </tbody>
      </table>
    </div>

    <Pagination :links="users.links" />
  </div>
</template>
