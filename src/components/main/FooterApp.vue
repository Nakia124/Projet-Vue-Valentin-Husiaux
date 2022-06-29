<template>
  <footer class="footer-app-component">
      <h1 class="is-size-4">Bienvenue {{ $store.getters.userinfo.name }}</h1>
  </footer>
</template>

<script>
/* 
  [CTRL] App.vue
  Define component controller
*/
  export default {
    name: 'FooterApp',

  }
</script>




