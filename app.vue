<script setup lang="ts">
const isColored = ref(true);

const onSelectOption = (param: boolean) => {
  isColored.value = param;
};
</script>

<template>
  <v-app>
    <!-- Sidebar -->
    <SideBar @selectOption="onSelectOption" />

    <!-- Cards -->
    <v-main>
      <ImageGallery :isColored="isColored" />
    </v-main>
  </v-app>
</template>

<style scoped>
* {
  font-family: "Inter";
}
</style>
