<template>
  <v-app >
    <v-navigation-drawer
      persistent
      v-model="drawer"
      enable-resize-watcher
    >
      <v-toolbar>
          <v-flex>
            <v-text-field
              name="input-2-3"
              label="Search"
              class="input-group--focused"
              append-icon="search"
              single-line
            ></v-text-field>
          </v-flex>
      </v-toolbar>
      <v-list two-line>
        <template v-for="item in items.slice(0, 6)">
          <v-subheader v-if="item.header" v-text="item.header"></v-subheader>
          <v-divider v-else-if="item.divider" v-bind:inset="item.inset"></v-divider>
          <v-list-tile avatar v-else>
            <v-list-tile-avatar>
              <img v-bind:src="item.avatar" />
            </v-list-tile-avatar>
            <v-list-tile-content>
              <v-list-tile-title v-html="item.title"></v-list-tile-title>
              <v-list-tile-sub-title v-html="item.subtitle"></v-list-tile-sub-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed>
      <v-toolbar-side-icon @click.native.stop="drawer = !drawer" light></v-toolbar-side-icon>
      <v-toolbar-title v-text="title" v-bind:style="styleTitle"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        icon
        light
        @click.native.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>more_vert</v-icon>
      </v-btn>
    </v-toolbar>
    <main>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
      <v-spacer></v-spacer>
      <v-bottom-nav
        class="transparent"
        absolute value="true">
          <v-text-field
            name="input-2-3"
            label="Write Something"
            class="input-group--focused"
            single-line
          ></v-text-field>
      </v-bottom-nav>
    </main>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { header: 'Today' },
          { avatar: '/static/v.png', title: 'Brunch this weekend?', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
          { divider: true, inset: true },
          { avatar: '/static/v.png', title: 'Brunch this weekend?', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
          { divider: true, inset: true },
          { avatar: '/static/v.png', title: 'Brunch this weekend?', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
          { divider: true, inset: true },
          { avatar: '/static/v.png', title: 'Brunch this weekend?', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
          { divider: true, inset: true },
          { avatar: '/static/v.png', title: 'Brunch this weekend?', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
          { divider: true, inset: true }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'SimCat',
        styleTitle: {
          color: '#010066'
        }
      }
    }
  }
</script>

<style lang="stylus">
  @import './stylus/main'
</style>
