<template>
  <v-app>
    <LeftNav />
    <v-toolbar
      app
      :clipped-left="clipped"
    >
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon v-html="miniVariant ? 'fa-chevron-right' : 'fa-chevron-left'"></v-icon>
      </v-btn>
      <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>fa-globe</v-icon>
      </v-btn>
      <v-btn icon @click.stop="fixed = !fixed">
        <v-icon>fa-minus</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>fa-bars</v-icon>
      </v-btn>
    </v-toolbar>
    <v-content>
      <HelloWorld msg="Hello World!!!"/>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import LeftNav from './components/organisms/LeftNav.vue';
import HelloWorld from './components/HelloWorld.vue';

@Component({
  components: {
    HelloWorld,
    LeftNav
  }
})
export default class App extends Vue {
  clipped: boolean = false
  drawer: boolean = true
  miniVariant: boolean = false
  right: boolean = true
  rightDrawer: boolean = false
  title: string = 'Vuetify.js'
  constructor() {
    super();
    console.log(process.env);
  }
}
</script>
