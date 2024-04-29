<template>
  <q-layout
    view="lHh Lpr lff"
    container
    style="height: 100vh; overflow: auto"
    class="shadow-2"
  >
    <AppHeader @drawer-btn-click="drawer = !drawer" />

    <q-drawer
      v-model="drawer"
      show-if-above
      :mini="false"
      :width="300"
      :breakpoint="500"
    >
      <SideDrawer />
    </q-drawer>

    <q-page-container>
      <q-page class="bg-grey-1 q-px-lg q-py-md">
        <router-view />
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import SideDrawer from "components/SideDrawer.vue";
import AppHeader from "components/AppHeader.vue";
import { ref } from "vue";

const drawer = ref(false);
</script>
