<template>
   <v-app-bar
      app
      flat
    >

      <v-toolbar-title v-if="!isMobileSearched">
        <v-img width="120" src="~/assets/logo.png"></v-img>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <!-- <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn> -->
        <v-btn v-if="!isMobileSearched" icon>
            <v-icon  @click="isMobileSearched = true">mdi-magnify</v-icon>
        </v-btn>
        <v-col 
            v-else 
            cols="12"
            class="text-center"
        >
            <v-text-field 
                placeholder="Search" 
                variant="outlined"
                color="primary"
                prepend-icon="mdi-arrow-left"
                class="primary"
                @click:prepend="isMobileSearched = false"
                hide-details 
                rounded 
                size="dense"
                single-line 
            >
            </v-text-field>
        </v-col>

      <template v-slot:extension>
        <v-row align="center" no-gutters>
            <v-col 
              v-for="menu in menus"
              :key="menu.name"
              :class="{ 'active-col': $route.path === menu.path }" 
              @click="$router.push(menu.path)"
              class="py-2 pointer text-center" 
            >
                <v-icon 
                  :class="{ 'active-button': $route.path === menu.path }" 
                  size="35"
                >{{ menu.icon }}</v-icon>
            </v-col>
          </v-row>
      </template>
    </v-app-bar>
</template>

<script setup>
  import { useDisplay } from 'vuetify'

  const { smAndDown, mdAndUp, xlAndUp } = useDisplay()

  const isMobileSearched = ref(false)
  const menus = ref([
    { name: 'Home', icon: 'mdi-home-variant-outline', path: '/' },
    { name: 'Messages', icon: 'mdi-comment-outline', path: '/messages' },
    { name: 'Account', icon: 'mdi-account-outline', path: '/account' },
    { name: 'Notifications', icon: 'mdi-bell-outline', path: '/notifications' },
  ])
</script>

<style scoped>
.active-button {
  color: #4527A0; 
  background-color: transparent !important;
}
.active-col {
  border-bottom: 6px solid #4527A0;
}
.v-btn::before {
  background-color: transparent;
}

</style>