<script setup lang="ts">
const { isColored } = defineProps({
  isColored: Boolean,
});

const copyUrl = async (url: string) => await navigator.clipboard.writeText(url);
</script>

<template>
  <v-card class="pa-3 ma-6" elevation="6">
    <v-row no-gutters>
      <!-- Generate n children, each taking up {cols} span  -->
      <v-col v-for="n in 200" cols="1" sm="3" md="2" lg="1">
        <v-hover v-slot="{ isHovering, props }">
          <v-card
            :elevation="isHovering ? 24 : 1"
            v-bind="props"
            class="ma-1"
            @click="
              copyUrl(
                `https://picsum.photos/500/300?image=${n * 5 + 10}${
                  isColored ? '' : '&grayscale'
                }`
              )
            "
          >
            <v-img
              :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${
                isColored ? '' : '&grayscale'
              }`"
              :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${
                isColored ? '' : '&grayscale'
              }`"
              aspect-ratio="1"
              cover
            >
              <template v-slot:placeholder>
                <v-row class="fill-height" align="center" justify="center">
                  <v-progress-circular indeterminate color="grey-lighten-5" />
                </v-row>
              </template>
            </v-img>
          </v-card>
        </v-hover>
      </v-col> </v-row
  ></v-card>
</template>
