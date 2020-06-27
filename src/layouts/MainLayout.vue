 Layout Builder
Visible Header
Visible Footer
Visible left-side Drawer
Visible right-side Drawer
Inject Drawer content for scrolling
<template>
  <q-layout view="hHh lpR fFf">

    <q-header elevated class="bg-red-12 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar square>
            <img src="https://image.flaticon.com/icons/svg/869/869636.svg">
          </q-avatar>
          Deep Web
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>
