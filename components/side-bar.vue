<script setup lang="ts">
const emits = defineEmits(["selectOption"]);
</script>

<template>
  <v-navigation-drawer expand-on-hover rail>
    <v-list>
      <v-list-item
        prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
        title="Ben Dover"
        subtitle="ben_dover@hotmail.com"
      ></v-list-item>
    </v-list>

    <v-divider />

    <v-list density="compact" nav>
      <v-list-item
        prepend-icon="mdi-image"
        title="Color Gallery"
        value="color"
        @click="() => {emits('selectOption', true)}"
      />
      <v-list-item
        prepend-icon="mdi-dialpad"
        title="Grayscale Gallery"
        value="grayscale"
        @click="() => {emits('selectOption', true)}"
      />
    </v-list>
  </v-navigation-drawer>
</template>
