<template>
    <v-app id="inspire">
      <v-navigation-drawer v-model="drawer">
      </v-navigation-drawer>
  
      <v-app-bar>
  
        <v-toolbar-title>Consultorio Juridico </v-toolbar-title>

        <v-btn prepend-icon="mdi-login" variant="outlined"> <NuxtLink to="/login"> Iniciar Sesion  </NuxtLink></v-btn>


      </v-app-bar>
  
      <v-main>
      </v-main>
    </v-app>
  </template>