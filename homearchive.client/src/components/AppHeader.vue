<template>
<v-app-bar :elevation="2" color="primary" app>
    <v-app-bar-nav-icon></v-app-bar-nav-icon>
    <v-app-bar-title>HomeArchive</v-app-bar-title>

    <!-- Theme switch -->
    <v-btn @click="changeTheme">
        <v-icon>{{ themeIcon }}</v-icon>
    </v-btn>
</v-app-bar>
</template>

<script setup>
import { onBeforeMount, ref } from 'vue';
import { useTheme } from 'vuetify';

const theme = useTheme();
const themeIcon = ref('mdi-weather-night');

onBeforeMount(() => {
    themeIcon.value = theme.global.current.value.dark ? 'mdi-weather-sunny' : 'mdi-weather-night';
});

const changeTheme = () => {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark';
  themeIcon.value = theme.global.current.value.dark ? 'mdi-weather-sunny' : 'mdi-weather-night';
};
</script>