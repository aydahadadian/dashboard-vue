<template
>
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
</template>


<script lang="jsx">

export default {
    data: () => ({

        profileItems: [
            {
                avatar: true,
                items: [{ title: "List Item" }],
                title: "Broklyn alice",
            },
        ],
        dashboardItems: [
            {
                action: "mdi-view-dashboard",
                items: [{ title: "List Item" }],
                title: "Dashboard",
            },
        ],
        items: [
            {
                action: "mdi-image",
                items: [{ title: "List Item" }],
                title: "Pages",
            },
            {
                action: "mdi-apps",
                active: true,
                items: [
                    { title: "Breakfast & brunch" },
                    { title: "New American" },
                    { title: "Sushi" },
                ],
                title: "Application",
            },
            {
                action: "mdi-basket",
                items: [{ title: "List Item" }],
                title: "Ecommerce",
            },
            {
                action: "mdi-clipboard-outline",
                items: [{ title: "List Item" }],
                title: "Authentication",
            },
        ],
        docs: [
            {
                action: "mdi-user",
                title: "Getting Started",
            },
            {
                action: "mdi-cube-scan",
                active: true,
                title: "Components",
            },
            {
                action: "mdi-note-text-outline",
                active: true,
                title: "Changelog",
            },
        ]
    }),

}
</script>