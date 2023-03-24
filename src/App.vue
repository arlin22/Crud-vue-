<script>
import Formulaire from './components/Formulaire.vue';
import UserInfo from './components/UserInfo.vue';
export default{
  
    name: "app",
    
    components: { 
      Formulaire,UserInfo
     },
     data:function() {
      users: []
     },
     methods: {
      addUser:function(newUser) {
      console.log("called", newUser);
      this.users.push(newUser);
    }
     },
}
</script>

<template>
  <div id="app">
    <Formulaire/>
  </div>
 
</template>

<style>
.adduser{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    
.app{
  margin-top: 0;
}

</style>
