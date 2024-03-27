<template>
    <v-app>
        <p>
            Less Layout
        </p>
        <v-main>
            <slot />
        </v-main>
    </v-app>
</template>

<script setup>
  import AppBar from '../components/NavigationComponents/AppBar.vue'
</script>