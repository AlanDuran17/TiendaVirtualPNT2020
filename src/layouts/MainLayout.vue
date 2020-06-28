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
          <div class="text-h6">
            <img src="~assets/logo_market.png" width="40px" height="auto" class="vertical-middle">
            Free Market
          </div>
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

<style>
  body{
    background-color: rgb(228, 228, 228);
  }
</style>
