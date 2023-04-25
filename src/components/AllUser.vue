<template>
    <div class="container">
      <ul>
        <label for="">Kullanıcı Adı</label>
        <li class="username" v-for="item,index in myData" :key="index">
            <!-- <router-link to="/users" class="nav-link">Users</router-link> -->
            {{ item.username }} 
        </li>  
      </ul>
      <ul>
        <label for="">Şifre</label>
        <li class="password" v-for="item,index in myData" :key="index">
            <!-- <router-link to="/users" class="nav-link">Users</router-link> -->
             {{ item.password }}
        </li>
      </ul>
    </div>   
</template>

<script>


export default {
  data : function(){
    return{
      myData:null
    }
  },
  mounted: async function(){
    var resp = await fetch(
      'http://localhost:8080/users/user',
    { 
      method : 'GET' , 
    headers: {
      "Content-Type": "application/json",
      // 'Content-Type': 'application/x-www-form-urlencoded',
    },
    
     }
    )
   this.myData = await resp.json()
  }

}
</script>

<style>
.container {
  width: 400px;
  height: 300px;
  display: flex;
  margin: auto;
}

.username {
  width: 200px;
  height: 40px;
  border: 1px solid black;
  text-align: center;
}
.password {
  width: 200px;
  height: 40px;
  border: 1px solid rgb(31, 28, 28);
  text-align: center;
}</style>