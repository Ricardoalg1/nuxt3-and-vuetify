<template>
    <v-app id="inspire">
      <v-system-bar>
        <v-spacer></v-spacer>
  
        <v-icon>mdi-square</v-icon>
  
        <v-icon>mdi-circle</v-icon>
  
        <v-icon>mdi-triangle</v-icon>
      </v-system-bar>
  
          <v-navigation-drawer v-model="drawer">
            <v-sheet
              color="grey-lighten-4"
              class="pa-4"
            >
              <v-avatar
                class="mb-4"
                color="grey-darken-1"
                size="64"
              ></v-avatar>
  
              <div>monitor</div>
            </v-sheet>
  
            <v-divider></v-divider>
  
            <v-list>
              <v-list-item
                v-for="[icon, text] in links"
                :key="icon"
                link
              >
                <template v-slot:prepend>
                  <v-icon>{{ icon }}</v-icon>
                </template>
  
                <v-list-item-title>{{ text }}</v-list-item-title>
              </v-list-item>
            </v-list>
            
          </v-navigation-drawer>
  
      <v-main>
        <v-container>



        </v-container>

      </v-main>
    </v-app>
  </template>
  
  <script>
    export default {
      data: () => ({
        drawer: null,
        links: [
          ['mdi-inbox-arrow-down', 'Inbox'],
          ['mdi-send', 'Send'],
          ['mdi-delete', 'Trash'],
          ['mdi-alert-octagon', 'Spam'],
        ],
      }),

    }
  </script>
  
  
  <style lang="scss">
  @use './settings';
  </style>
  