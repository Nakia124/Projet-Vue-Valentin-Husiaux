<template>
  <header class="header-app-component-section">
    <div v-if="cmpUserinfo">
        <ul class="navbar">
            <li class="navbar-item"><router-link :to="{ name: 'DashboardView' }">Accueil</router-link></li>
            <li class="navbar-item" ><router-link :to="{ name: 'CreateView' ,params: { type: 'snapshoot' } }">Créer une photo </router-link></li>
            <li class="navbar-item" ><router-link :to="{ name: 'CreateView' ,params: { type: 'album' } }">Créer Album </router-link></li>
            
         <button 
          class="buttonDeconnexion"
          v-text="`Déconnexion`"
          @click.prevent="$emit('onLogout', true)"
       />
       </ul>
        <p 
          v-if="cmpSnapshootlist.length"
        >
          Nombre de photos <b>{{cmpSnapshootlist.length}}</b>
        </p>
        </div>
       
  </header>
</template>

<script>
/* 
  [CTRL] App.vue
  Define component controller
*/
  export default {
    name: 'HeaderApp',

    /* 
      [VUE] Props
      Data binding from parent component
    */
      props: {
        userinfo: {
          type: Object,
          required: false,
          default: () => null
        },
        snapshootlist: {
          type: Array,
          required: false,
          default: () => []
        }
      },
    //

    /* 
      [VUE] Computed
      Used to have version of property value
    */
      computed: {
        cmpUserinfo: function(){ return this.userinfo },
        cmpSnapshootlist: function(){ return this.snapshootlist },
      },
    //
  }
//
</script>