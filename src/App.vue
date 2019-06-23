<template>
  <div class="container m-2">
    <!-- <app-header></app-header> 
    <hr> -->
    <!-- <div class="row">
      <servers></servers>
      <app-server-details></app-server-details>
    </div>
    <hr> -->
  <!--   <app-footer></app-footer> -->
  <!-- User -->
  <div class="row justify-content-md-center">
    <div class="col-xs-12">
        <app-user></app-user>
    </div>
  </div>
  </div>
</template>

<script>
  //import Header from './components/Shared/Header.vue';
  //import Footer from './components/Shared/Footer.vue';
  //import Servers from './components/Servers/Servers.vue';
  //import ServerDetails from './components/Servers/ServerDetails.vue';
  import User from './components/User.vue';
  export default {
    components: {
      // appHeader: Header,
      // Servers,
      // 'app-server-details': ServerDetails,
      // 'app-footer': Footer
      appUser: User
    }
  }
</script>

<style>
  div.component{
    border: 1px solid black;
    padding: 30px;

  }
</style>
