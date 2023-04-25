<template>
   <div class="container"> 
    <form @submit="addUser">
    
      <div>
        <label for="firstName">Adınız</label>
        <input type="text" id="firstName" v-model="user.firstName" required>
      </div>
      <div>
        <label for="password">Şifreniz</label>
        <input type="text" id="password" v-model="user.password" required>
      </div>
      <button type="submit" @click="addUser">Kullanıcı Ekle</button>
    
    </form>
</div>
  </template>

<script>
export default {
  data() {
    return {
        myData : null ,
        user: {
            firstName: '',
            lastName: '',
        }
    }
  },
  methods: {
    async addUser() {
      const response = await fetch(
        '/http://localhost:8080/users/', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(this.user)
      })
      this.myData = await response.json()
    }
  }
}
</script>

<style></style>