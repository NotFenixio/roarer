<script setup lang="ts">
import Login from "./Login.vue";
import { useLocationStore } from "../stores/location";

const { title } = defineProps<{
  title: string;
}>();

document.title = "Roarer - " + title;

const locationStore = useLocationStore();
</script>

<template>
  <div>
    <div class="space-x-2">
      <h1 class="inline-block text-3xl font-bold">Roarer - {{ title }}</h1>
      <Login />
      <div class="float-right space-x-2">
        <button
          class="text-sky-400 underline"
          @click="locationStore.location = 'home'"
        >
          Home
        </button>
        <button
          class="text-sky-400 underline"
          @click="locationStore.location = 'group'"
        >
          Groups
        </button>
      </div>
    </div>
    <p>
      Note: Roarer is very early in its development. Please do report bugs
      and/or suggest features!
    </p>
  </div>
</template>