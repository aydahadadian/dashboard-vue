<template>
  <v-app id="inspire">
    <v-layout style="height: 100vh">
      <v-navigation-drawer
        v-model="drawer"
        dark
        class="rounded-lg floating sticky"
      >
        <v-sheet class="pa-6" style="background: transparent">
          <div>Material dashboard</div>
        </v-sheet>

        <v-divider></v-divider>

        <v-list :lines="false" density="compact" nav>
          <v-list-group
            class="px-4 rounded-lg"
            v-for="item in profileItems"
            :key="item.title"
            v-model="item.active"
            :prepend-icon="item.action"
            no-action
          >
            <template v-slot:activator>
              <v-list-item-content>
                <v-avatar size="36px">
                  <v-img
                    v-if="true"
                    alt="Avatar"
                    src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                  ></v-img>
                </v-avatar>
                <v-list-item-title
                  v-text="item.title"
                  style="flex:none"
                ></v-list-item-title>
              </v-list-item-content>
            </template>

            <v-list-item v-for="child in item.items" :key="child.title">
              <v-list-item-content>
                <v-list-item-title v-text="child.title"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-group>

          <v-divider class="py-2"></v-divider>

          <v-list-group
            class="px-4 rounded-lg"
            v-for="item in dashboardItems"
            :key="item.title"
            v-model="item.active"
            :prepend-icon="item.action"
            no-action
          >
            <template v-slot:activator>
              <v-list-item-content>
                <v-list-item-title v-text="item.title"></v-list-item-title>
              </v-list-item-content>
            </template>

            <v-list-item v-for="child in item.items" :key="child.title">
              <v-list-item-content>
                <v-list-item-title v-text="child.title"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-group>

          <v-subheader :inset="inset">
            Pages
          </v-subheader>
          <v-list-group
            class="px-4 rounded-lg"
            v-for="item in items"
            :key="item.title"
            v-model="item.active"
            :prepend-icon="item.action"
            no-action
          >
            <template v-slot:activator>
              <v-list-item-content>
                <v-list-item-title v-text="item.title"></v-list-item-title>
              </v-list-item-content>
            </template>

            <v-list-item v-for="child in item.items" :key="child.title">
              <v-list-item-content>
                <v-list-item-title v-text="child.title"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-group>
          <v-divider></v-divider>
          <v-subheader :inset="inset">
            Docs
          </v-subheader>

          <v-list-item
            v-for="(item, i) in docs"
            :key="i"
            :value="item"
            active-color="primary"
          >
            <template v-slot:prepend>
              <v-icon :icon="item.action"></v-icon>
            </template>

            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-main style="padding-left: 280px;flex:1 0">
        <v-app-bar title="Application bar"> </v-app-bar>
        <v-container class="py-8 px-6" fluid>
          <v-row>
            <v-col v-for="card in cards" :key="card" cols="12">
              <v-card> </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>
    </v-layout>
  </v-app>
</template>

<script lang="jsx">
export default {
  data: () => ({
    cards: ['Today', 'Yesterday'],
    drawer: null,
    open: ['Users'],
    profileItems: [
        {
          avatar: true,
          items: [{ title: 'List Item' }],
          title: 'Broklyn alice',
        },
    ],
    dashboardItems: [
        {
          action: 'mdi-view-dashboard',
          items: [{ title: 'List Item' }],
          title: 'Dashboard',
        },
    ],
    items: [
        {
          action: 'mdi-image',
          items: [{ title: 'List Item' }],
          title: 'Pages',
        },
        {
          action: 'mdi-apps',
          active: true,
          items: [
            { title: 'Breakfast & brunch' },
            { title: 'New American' },
            { title: 'Sushi' },
          ],
          title: 'Application',
        },
        {
          action: 'mdi-basket',
          items: [{ title: 'List Item' }],
          title: 'Ecommerce',
        },
        {
          action: 'mdi-clipboard-outline',
          items: [{ title: 'List Item' }],
          title: 'Authentication',
        },

      ],
      docs: [
        {
          action: 'mdi-user',
          title: 'Getting Started',
        },
        {
          action: 'mdi-cube-scan',
          active: true,
          title: 'Components',
        },
        {
          action: 'mdi-note-text-outline',
          active: true,
          title: 'Changelog',
        },
    ]
  }),
}
</script>

<style>
#inspire > .v-application--wrap {
  flex-direction: row;
}
.v-navigation-drawer {
  left: 0px;
  transform: translateX(0%);
  position: fixed;
  height: 100vh;
  top: 24px;
  bottom: 0px;
  width: 256px;
  margin: 1rem;
  z-index: 10;
}
.v-app-bar {
  background: transparent;
  box-shadow: none;
}
.v-list-item__content {
  flex-wrap: nowrap;
  overflow: visible;
  min-width: 95px;
}
.v-list-item__content > .v-avatar {
  flex: none;
  margin-right: 10px;
}
.v-list-item .v-list-item__title,
.v-list-item .v-list-item__subtitle {
  font-size: 0.9rem;
}

.v-list-item--link:before {
  content: none;
}
.v-list-item {
  margin: 10px 0;
}
.v-list-item:hover {
  background-color: #4a4a4c !important;
  border-radius: 10px;
}
.v-list-item__icon {
  margin: 12px 0;
  margin-right: 12px !important;
}
.v-icon.v-icon {
  font-size: 1.3rem;
}
</style>
