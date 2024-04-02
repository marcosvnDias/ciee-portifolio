<script>
  import AlertPage from "./components/AlertPage.vue"
  import Sidebar from "./components/Sidebar.vue"

  export default {
    name: "App",
    components: { AlertPage, Sidebar },
    data() {
      return {
        alertOpen: true,
        openPages: false,
      }
    },
    methods : {
      closePageAlert() {
        this.alertOpen = false;
        this.openPages = true;
      }
    }
  }
</script>

<template>
  <div class="container">
    <AlertPage v-if="alertOpen" @close="closePageAlert"/>
    <Sidebar v-if="openPages"/>
  </div>
</template>

