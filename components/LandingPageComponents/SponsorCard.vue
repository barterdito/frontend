<template>
    <v-row v-if="mdAndUp" class="pt-3 pl-1">
        <v-col v-if="xlAndUp" cols="7"></v-col>
        <v-col xl="5" class="pl-7">
            <!-- <v-card class="mb-4" flat>
                <v-card-title class="text-center text-primary font-weight-medium mb-4">
                    Top Traders
                </v-card-title>
                <v-row v-for="i in 11" :key="i" class="mb-4 align-center" no-gutters >
                    <v-col cols="1" class="ml-2">
                        <p class="mb-0">{{ `${i}.` }}</p>
                    </v-col>
                    <v-col cols="2" class="">
                        <v-avatar
                            size="36px"
                        >
                            <v-img
                            alt="Avatar"
                            src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                            ></v-img>
                        </v-avatar>
                    </v-col>
                    <v-col> 
                        <p class="mb-0 font-weight-bold">John Patrick</p>
                        <p class="mb-0 text-caption text-disabled">3 barters this week</p>
                    </v-col>
                    
                    <v-divider v-if="i !== 11" class="mt-2 mx-4"></v-divider>
                </v-row>
            </v-card> -->
            <v-card class="py-2 px-4">
                
                <v-row class="align-center mb-2" no-gutters>
                    <p class="mb-0 text-primary"> Top Traders</p>
                    <v-spacer></v-spacer>
                    <p class="mb-0 text-body-2 text-disabled"> See all</p>
                </v-row>
                <v-sheet v-for="i in 4" :key="i" class="pa-4 mb-3 elevation-4">
                    <v-avatar
                        size="40px"
                    >
                        <v-img
                            alt="Avatar"
                            src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                        ></v-img>
                    </v-avatar>

                    <p class="mb-0">John Patrick <v-icon size="15" color="#0D47A1">mdi-check-circle</v-icon></p>
                    <p class="mb-0 text-caption text-grey">11 barters this week</p>
                </v-sheet>
            </v-card>
        </v-col>
    </v-row>
</template>

<script setup>
  import { useDisplay } from 'vuetify'

  const isLoading = ref(true)

  const { mdAndUp, xlAndUp } = useDisplay()
</script>