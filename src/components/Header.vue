<template>
  <v-app dark>
    <v-layout wrap>
      <v-container>
        <v-layout justify-center>
          <v-btn color="pink" dark @click.stop="drawer = !drawer">Menu</v-btn>
        </v-layout>
      </v-container>
      <v-navigation-drawer v-model="drawer" absolute temporary>
        <v-list class="pa-1">
          <v-list-tile avatar>
            <v-list-tile-avatar>
              <img src="https://randomuser.me/api/portraits/men/85.jpg">
            </v-list-tile-avatar>
            <v-list-tile-content>
              <v-list-tile-title>John Leider</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
        <v-list class="pt-0" dense>
          <v-list-tile v-for="item in items" :key="item.title" @click="">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
    </v-layout>
  </v-app>
  <!--<v-app>-->
    <!--<v-navigation-drawer-->
      <!--persistent-->
      <!--:mini-variant="miniVariant"-->
      <!--:clipped="clipped"-->
      <!--v-model="drawer"-->
      <!--enable-resize-watcher-->
      <!--fixed-->
      <!--app-->
    <!--&gt;-->
      <!--<v-list>-->
        <!--<v-list-tile-->
          <!--value="true"-->
          <!--v-for="(item, i) in items"-->
          <!--:key="i"-->
        <!--&gt;-->
          <!--<v-list-tile-action>-->
            <!--<v-icon v-html="item.icon"></v-icon>-->
          <!--</v-list-tile-action>-->
          <!--<v-list-tile-content>-->
            <!--<v-list-tile-title v-text="item.title"></v-list-tile-title>-->
          <!--</v-list-tile-content>-->
        <!--</v-list-tile>-->
      <!--</v-list>-->
    <!--</v-navigation-drawer>-->
    <!--<v-toolbar-->
      <!--app-->
      <!--:clipped-left="clipped"-->
    <!--&gt;-->
      <!--<v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>-->
      <!--<v-btn icon @click.stop="miniVariant = !miniVariant">-->
        <!--<v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>-->
      <!--</v-btn>-->
      <!--<v-btn icon @click.stop="clipped = !clipped">-->
        <!--<v-icon>web</v-icon>-->
      <!--</v-btn>-->
      <!--<v-btn icon @click.stop="fixed = !fixed">-->
        <!--<v-icon>remove</v-icon>-->
      <!--</v-btn>-->
      <!--<v-toolbar-title v-text="title"></v-toolbar-title>-->
      <!--<v-spacer></v-spacer>-->
      <!--<v-btn icon @click.stop="rightDrawer = !rightDrawer">-->
        <!--<v-icon>menu</v-icon>-->
      <!--</v-btn>-->
    <!--</v-toolbar>-->
    <!--<v-content>-->
      <!--<router-view/>-->
    <!--</v-content>-->
    <!--<v-navigation-drawer-->
      <!--temporary-->
      <!--:right="right"-->
      <!--v-model="rightDrawer"-->
      <!--fixed-->
      <!--app-->
    <!--&gt;-->
      <!--<v-list>-->
        <!--<v-list-tile @click="right = !right">-->
          <!--<v-list-tile-action>-->
            <!--<v-icon>compare_arrows</v-icon>-->
          <!--</v-list-tile-action>-->
          <!--<v-list-tile-title>Switch drawer (click me)</v-list-tile-title>-->
        <!--</v-list-tile>-->
      <!--</v-list>-->
    <!--</v-navigation-drawer>-->
    <!--<v-footer :fixed="fixed" app>-->
      <!--<span>Copyright &copy; 2018</span>-->
    <!--</v-footer>-->
  <!--</v-app>-->
</template>

<script>
  export default {
    name: 'Header',
    data () {
      return {
        items: [
          { title: 'Home', icon: 'dashboard' },
          { title: 'About', icon: 'question_answer' }
        ],
        drawer: null,
        // clipped: false,
        // drawer: true,
        // fixed: false,
        // items: [{
        //   icon: 'bubble_chart',
        //   title: 'Inspire'
        // }],
        // miniVariant: false,
        // right: true,
        // rightDrawer: false,
        // title: 'Vuetify.js',
      }
    },
  }
</script>
