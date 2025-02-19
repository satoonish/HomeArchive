<template>
  <v-app>
    <AppHeader/>

    <v-main>
      <NoteBook/>
    </v-main>

    <AppFooter/>
  </v-app>
</template>

<script lang="ts" setup>
import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';
import NoteBook from './components/NoteBook.vue';
</script>
