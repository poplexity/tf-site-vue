<template>
    <span>
        <v-navigation-drawer app v-model="drawer" class="#f6f1e1" disable-resize-watcher>
            <v-list>
                <template v-for="(item, index) in items">
                    <v-list-tile :key="index" @click="item.click">
                        <v-list-tile-content>
                            {{item.title}}
                        </v-list-tile-content>
                    </v-list-tile>
                    <v-divider :key="`divider-${index}`"></v-divider>
                </template>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar app color="#f6f1e1">
            <v-toolbar-side-icon class="hidden-md-and-up" @click="drawer = !drawer"></v-toolbar-side-icon>
            <v-spacer class="hidden-md-and-up"></v-spacer>
            <v-toolbar-title>{{appTitle}}</v-toolbar-title>
            <v-btn flat class="hidden-sm-and-down" @click="goAbout">About</v-btn>
            <v-spacer class="hidden-sm-and-down"></v-spacer>
            <v-btn flat class="hidden-sm-and-down" @click="goHome">Home</v-btn>
            <v-btn color="#f6f1e1" class="hidden-sm-and-down" @click="goWhyTelos">Why Telos?</v-btn>
        </v-toolbar>
    </span>
</template>

<script>
export default {
  name: 'AppNavigation',
  data () {
    return {
      appTitle: 'Telos Foundation',
      drawer: false,
      items: [
        { title: 'Home', click: this.goHome },
        { title: 'About', click: this.goAbout },
        { title: 'Why Telos?', click: this.goWhyTelos }
      ]
    }
  },
  methods: {
    goHome () {
      this.$router.push({ name: 'home' })
    },
    goAbout () {
      this.$router.push({ name: 'about' })
    },
    goWhyTelos () {
      console.log('GO WHY TELOS')
    }
  }
}
</script>

<style scoped>
</style>
