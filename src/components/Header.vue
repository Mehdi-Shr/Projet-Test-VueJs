<template>
  <header>
    <nav class="uk-navbar-container uk-margin" uk-navbar>
      <div class="uk-navbar-left">
        <RouterLink to="/">Comparateur d'eaux</RouterLink>
      </div>
      <div class="uk-navbar-right">

        <div class="uk-navbar-item">
          <RouterLink to="/">Liste des produits</RouterLink>
        </div>


        <template v-if="!$store.getters.isConnected">
          <div class="uk-navbar-item">
            <RouterLink to="/connexion">Connexion</RouterLink>
          </div>

          <div class="uk-navbar-item">
            <RouterLink to="/inscription">Inscription</RouterLink>
          </div>
        </template>
        <template v-else>
          <div class="uk-navbar-item">
            <RouterLink to="/product/new">Ajouter un produit</RouterLink>
          </div>
          <div class="uk-navbar-item">
            <RouterLink to="/user">Mon compte</RouterLink>
          </div>
          <button class="deconnexion" @click="deconnexion">
            Déconnexion
          </button>
        </template>

      </div>

    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
  components: {},
  methods: {
    deconnexion() {
      this.$store.dispatch("deconnexion")
    }
  }
}
</script>

<style scoped>
header {
  margin-bottom: 100px;
}
nav {
  padding: 25px;
  background-color: #02C39A!important;
}

nav a {
  color: white;
}

.uk-navbar-left a {
  color: white;
  font-size: 30px;
}

.deconnexion {
  padding: 15px;
  background-color: white!important;
  color: #02C39A;
  border: 0px;
  border-radius: 5px;
}
</style>