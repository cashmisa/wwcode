<template>
  <v-app>
    <v-navigation-drawer
      dark
      persistent
      :clipped="clipped"
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
        <span v-for="i in menuItems" :key="i.title">
        <v-list-tile   
        :to="i.path"
        v-if="!i.children">
          <v-list-tile-action>
            <v-icon>{{i.icon}}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title class="navtile" v-text="i.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>

        <v-list-group
        :title="i.title"
        v-else>
          <v-list-tile slot="activator">
            <v-list-tile-action>
              <v-icon>{{ i.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>
                {{ i.title }} <v-icon v-if="!i.ready" size="small" color="grey">build</v-icon>
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-list-tile
            class="navtile"
            v-for="c in i.children"
            :key="c.title"
            :to="c.path">
              <v-list-tile-action>
                <v-icon>{{c.icon}}</v-icon>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>
                  {{ c.title }}
                  <v-icon v-if="!c.ready" size="small" color="grey">build</v-icon>
                </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list-group>
        </span>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      app
      :clipped-left="clipped"
    >
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer/>
      <v-spacer/>

        <v-menu offset-y>
          <v-btn slot="activator" icon><v-icon>person</v-icon></v-btn>
          <v-list>
            <v-list-tile to="/login">
              <v-list-tile-title>Logout</v-list-tile-title>
            </v-list-tile>
          </v-list>
        </v-menu>

    </v-toolbar>
    <v-content>
      <slot/>
    </v-content>

    <v-footer>
      <v-spacer/><span>&copy; 2018</span><v-spacer/>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: true,
      fixed: false,
      menuItems: [
        { icon: "assignments", title: "All Jobs", path: "/" },
        {
          icon: "group",
          title: "Applicants",
          children: [
            { title: "All Applicants", path: "/applicant"}
          ]
        },
        {
          icon: "people_outline",
          title: "Talent Pool",
          ready: true,
          children: [{ title: "All Talents", path: "/talent", ready: true }]
        },
        {
          icon: "assessment",
          title: "Assessments",
          ready: true,
          children: [
            { title: "Create Assignment", path: "/assignment/create" },
            { title: "All Assignment", path: "/assignment/list", ready: true }
          ]
        },
        { icon: "settings", title: "Settings", path: "/settings" }
      ],

      miniVariant: false,
      title: "TechFolio"
    };
  },
  name: "App"
};
</script>

<style scoped>
.navtile {
  color: white;
}
</style>
