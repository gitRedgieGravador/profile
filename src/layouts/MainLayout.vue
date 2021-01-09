<template>
  <q-layout view="lHh Lpr lFf">
    <q-header bordered :style="darkheader? 'background: #24292e':''"  :class="darkheader?'text-white  q-pa-sm':'text-white  q-pa-sm overlay'">
      <q-toolbar :class="darkheader? '':'transparent'">
        <q-toolbar-title>
          Redgie Gravador
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <!-- <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer> -->

    <q-page-container>
      <div class="row n-100">
        <!-- <div class="col-4">

        </div> -->
        <div class="col-12" style="height: 100vh;">
          <q-carousel
            animated
            v-model="slide"
            infinite
            autoplay
            arrows
            transition-prev="slide-right"
            transition-next="slide-left"
            height="100vh"
          >
            <q-carousel-slide :name="1" img-src="../assets/laptop_coffee.jpg" class="flex flex-center" >
              <div class="q-mt-md text-center h3 text-h3 text-white">
                The right people<br>at the right time.
              </div>
            </q-carousel-slide>
            <q-carousel-slide :name="2" img-src="../assets/note_coffee.jpg" class="flex flex-center"  >
            <div class="q-mt-md text-center h3 text-h3 text-white">
                When God start blessing you,<br> mind your ego.
              </div>
            </q-carousel-slide>
            <q-carousel-slide :name="3" img-src="../assets/note_mobile.jpg" class="flex flex-center" >
            <div class="q-mt-md text-center h3 text-h3 text-white">
                When God start blessing you,<br> mind your ego.
              </div>
            </q-carousel-slide>
          </q-carousel>
          <template >
            <img src="../assets/profile.png" class="carousel-img">
          </template>
        </div>
      </div>
      <q-scroll-observer @scroll="onScroll" />
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
// import EssentialLink from 'components/EssentialLink.vue'

// const linksData = [
//   {
//     title: 'Docs',
//     caption: 'quasar.dev',
//     icon: 'school',
//     link: 'https://quasar.dev'
//   },
//   {
//     title: 'Github',
//     caption: 'github.com/quasarframework',
//     icon: 'code',
//     link: 'https://github.com/quasarframework'
//   },
//   {
//     title: 'Discord Chat Channel',
//     caption: 'chat.quasar.dev',
//     icon: 'chat',
//     link: 'https://chat.quasar.dev'
//   },
//   {
//     title: 'Forum',
//     caption: 'forum.quasar.dev',
//     icon: 'record_voice_over',
//     link: 'https://forum.quasar.dev'
//   },
//   {
//     title: 'Twitter',
//     caption: '@quasarframework',
//     icon: 'rss_feed',
//     link: 'https://twitter.quasar.dev'
//   },
//   {
//     title: 'Facebook',
//     caption: '@QuasarFramework',
//     icon: 'public',
//     link: 'https://facebook.quasar.dev'
//   },
//   {
//     title: 'Quasar Awesome',
//     caption: 'Community Quasar projects',
//     icon: 'favorite',
//     link: 'https://awesome.quasar.dev'
//   }
// ]
/* eslint-disable */
export default {
  name: 'MainLayout',
  // components: { EssentialLink },
  data () {
    return {
      darkheader: false,
      leftDrawerOpen: false,
      // essentialLinks: linksData,
      slide: 1,
      autoplay: true
    }
  },
  methods: {
    onScroll (info) {
      if(info.position > 800 && (info.direction === "down" || info.direction === "up")) this.darkheader = true
      else this.darkheader = false
    }
  }
}
</script>
<style scoped>
.carousel-img {
  position: relative;
  z-index: 1;
  height: 100vh;
  top: -100vh;
  /* background-image: url('../assets/profile.png'); */
  /* background-repeat: no-repeat; */
}
</style>