<template>
  <div class="home">
    <v-layout row >
      <v-flex xs12>
            <v-list two-line>
              <template v-for="item in items">
                <v-subheader v-if="item.header" v-text="item.header"></v-subheader>
                <v-divider v-else-if="item.divider" v-bind:inset="item.inset"></v-divider>
                <v-list-tile avatar v-else v-bind:key="item.title" href="javascript:;" download target="_blank">
                  <v-list-tile-avatar>
                    <img v-bind:src="item.avatar"></v-list-tile-avatar>
                  </v-list-tile-avatar>
                  <v-list-tile-content>
                    <v-list-tile-title v-html="item.title"></v-list-tile-title>
                    <v-list-tile-sub-title v-html="item.subtitle"></v-list-tile-sub-title>
                  </v-list-tile-content>
                </v-list-tile>
              </template>
            </v-list>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      items: [
        { avatar: '/static/v.png', title: '1', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
        { avatar: '/static/v.png', title: '2', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
        { avatar: '/static/v.png', title: '3', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
        { avatar: '/static/v.png', title: '4', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
        { avatar: '/static/v.png', title: '5', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
        { avatar: '/static/v.png', title: '6', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
        { avatar: '/static/v.png', title: '7', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
        { avatar: '/static/v.png', title: '8', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
        { avatar: '/static/v.png', title: '9', subtitle: "<span class='grey--text text--darken-2'>Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
