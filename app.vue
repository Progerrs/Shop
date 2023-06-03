<template>
  <div :class="{ 'dark': darkMode }">
    <div class="bg-white dark:bg-dim-900">
      <!-- App -->
      <div class="min-h-full">
        <div class="grid grid-cols-12 mx-auto sm:px-6 lg:max-w-7xl lg:px-8 lg:gap-5">
          <!-- Left sidebar -->
          <div class="hidden md:block xs-col-span-1 xl:col-span-2">
            <div class="sticky top-0">
              <sidebar-left @toggleDarkMode="toggleDarkMode"/>
            </div>
          </div>
          <!-- Main content -->
          <main class="col-span-12 md:col-span-8 xl:col-span-6">
            <router-view />
          </main>
          <!-- Right Sidebar -->
          <div class="hidden col-span-12 md:block xl:col-span-4 md:col-span-3">
            <div class="sticky top-0">
              <sidebar-right/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

let defaultTheme = true; // Define defaultTheme outside of the hook

const darkMode = ref(defaultTheme);

const toggleDarkMode = () => {
  darkMode.value = !darkMode.value;
  localStorage.setItem('darkMode', darkMode.value.toString());
};

onMounted(() => {
  const storedDarkMode = localStorage.getItem('darkMode');
  if (storedDarkMode !== null) {
    defaultTheme = storedDarkMode === 'true';
  } else {
    defaultTheme = true;
  }
  darkMode.value = defaultTheme;
});
</script>

