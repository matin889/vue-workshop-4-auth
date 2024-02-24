<template>
  <header>
    <div class="actions">
      <router-link v-if="!isLoggedIn" to="/login">Login</router-link>
      <button v-else @click="logout">Logout</button>
    </div>
  </header>
</template>

<script>
import { useAuthStore } from '@/stores/auth'
import { mapActions } from 'pinia'

export default {
  methods: {
    ...mapActions('auth', ['logout'])
  },
  computed: {
    isLoggedIn() {
      return useAuthStore().isLoggedIn
    }
  }
}
</script>

<style></style>
