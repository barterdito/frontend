<template>
    <v-app>
        <AppBar v-if="isLargeScreen" />
        <MobileAppBar v-if="isSmallScreen" />
        <v-main>
            <v-container fluid class="pa-0" style="background-color: #eee; min-height: 96vh; overflow: hidden;">
                <slot />
            </v-container>
        </v-main>
    </v-app>
</template>

<script setup>
  import AppBar from '../components/NavigationComponents/AppBar.vue'
  import MobileAppBar from '~/components/NavigationComponents/MobileAppBar.vue'

  import { useDisplay } from 'vuetify'

  const { mdAndUp, smAndUp, smAndDown } = useDisplay()

  const isSmallScreen = smAndDown.value

    const isLargeScreen = mdAndUp.value
</script>