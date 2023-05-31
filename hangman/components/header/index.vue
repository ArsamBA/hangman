<template>
   <v-app>
      <v-card>
      <v-layout>
         <!-- <v-system-bar color="deep-purple darken-3"></v-system-bar> -->
   
         <v-app-bar
            prominent
         >
            <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
   
            <v-toolbar-title>List Maker</v-toolbar-title>
   
            <v-spacer></v-spacer>
   
            <v-btn variant="text" icon="mdi-magnify"></v-btn>
   
            <v-btn variant="text" icon="mdi-filter"></v-btn>
   
            <v-btn variant="text" icon="mdi-dots-vertical"></v-btn>
         </v-app-bar>
   
         <v-navigation-drawer
            location="bottom"
            temporary
         >
         </v-navigation-drawer>
   
         <v-main style="height: 0px;">
            <v-card-text>
            The navigation drawer will appear from the bottom on smaller size screens.
            </v-card-text>
         </v-main>
      </v-layout>
      </v-card>
   </v-app>
</template>

<script setup lang="ts">

</script>

<style lang="scss">
@import '@/assets/scss/global.scss';
.v-app-bar.v-toolbar{
   background: none !important;
   color: $primary !important;
}

.mdi-menu,
.mdi-magnify,
.mdi-filter,
.mdi-dots-vertical {
   color: $primary !important;
}
</style>