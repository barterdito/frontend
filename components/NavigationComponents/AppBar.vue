<template>
    <v-app-bar
        app
        flat
    >
      <v-row align="center" class="mx-1">
        <v-col md="3" xl="4">
          <v-img width="150" src="~/assets/logo.png"></v-img>
        </v-col>

        <v-col md="6" xl="4" class="align-center text-center pa-0" >
          <v-row align="center" no-gutters>
            <v-col 
              v-for="menu in menus"
              :key="menu.name"
              :class="{ 'active-col': $route.path === menu.path }" 
              @click="$router.push(menu.path)"
              class="py-2 pointer" 
            >
                <v-icon 
                  :class="{ 'active-button': $route.path === menu.path }" 
                  size="35"
                >{{ menu.icon }}</v-icon>
            </v-col>
          </v-row>
        </v-col>

        <v-col v-if="mdAndUp" md="3"  xl="4" class="text-right pr-0">
          <v-row no-gutters align="center">
            <v-col v-if="xlAndUp" cols="6">

            </v-col>
            <v-col :cols="xlAndUp ? 6 : 12">
                
              <v-text-field 
              hide-details 
              placeholder="Search" 
              variant="outlined"
              rounded 
              dense 
              single-line 
              small
              color="primary"
              prepend-inner-icon="mdi-magnify"
              class="shrink ml-3"
            >
          </v-text-field>
            </v-col>
          </v-row>
        </v-col>
      </v-row>

      

      

      <!-- <template v-else>
        <v-btn v-if="!isMobileSearched" icon>
            <v-icon  @click="isMobileSearched = true">mdi-magnify</v-icon>
        </v-btn>
        <v-col 
            v-else 
            cols="12"
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
                dense 
                single-line 
                small
            >
            </v-text-field>
        </v-col>
      </template> -->
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
  border-bottom: 4px solid #4527A0;
}
.v-btn::before {
  background-color: transparent;
}

</style>