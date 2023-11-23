<template>
  <div class="container">
    <div>
      <h1 >AWS Amplify Congnito Authentication </h1>

      <!-- Unauthenticated -->
      <div v-if="!$auth.isAuthenticated">
        <nuxt-link to="/login" >Login</nuxt-link>
        <nuxt-link to="/register" >Register</nuxt-link>
      </div>

      <!-- Authenticated -->
      <div v-else>
        <p>You're logged in as {{ $auth.email }}</p>
        <button @click="$store.dispatch('auth/logout')" >Logout</button>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  components: {
    
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>