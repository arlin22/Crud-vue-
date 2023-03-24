<template >
<div class="info">  
    <h2>User info</h2>
    <form class="adduser" >
        <input v-model="Firstname" type="text" placeholder="Firstname">
        <input v-model="Lastname" type="text" placeholder="Lastname">
        <input v-model="Email" type="text" placeholder="Email">
        <input v-model="Age" type="text" placeholder="Age">
        <input v-model="Role"  type="text" placeholder="Role">
        <div class="add">
            <input v-model="skill" class="skills" type="text" placeholder="Skills">
            <button @click.prevent=" handleAddSkills" class="addSkills">+</button>
        </div>
        <div v-for="(skill,index) in Skills" :key="index" class="showskill">
            <p>{{skill}}</p>
            <img class="remove" @click="remove" src="../assets/delete.png" >
        </div>
        <label class="experience">
            <input v-model="Title"  type="text" placeholder="Experience Title">
            <input v-model="Description" class="descri" type="text" placeholder="Experience description">
            <input v-model="Time" type="text" placeholder="Experience date">
        </label>
        <button @click.prevent=" " class="addexperience">+</button>
        
    </form>
</div>
  
</template>
<script>
export default {
    name: 'Formulaire',
    data: function () {
        return {
            Firstname:'',
            Lastname:'',
            Email:'',  
            Age:'',
            Role:'',
            Skills:[],
            skill:'',
            Title:'',
            Description:'',
            Time:'',
            Experience:[],
            newExperience:'',
        }
    },
    methods: {
        handleAddUser() {
            this.$emit('addUser',{Firstname:this.Firstname,Lastname:this.Lastname,Email:this.Email, Age:this.Age,Age:this.Age, Role:this.Role,Title:this.Title,Description:this.Description,Time:this.Time})
           
        },
        handleAddSkills() {
            this.Skills.push(this.skill);
            
        },
        remove(index){
            this.Skills.splice(index,1);
        },
        
    }
}
</script>
<style >
.adduser{
display: flex;
gap: 25px;
}
  input{
    width:286px;
    height: 45px;

  }
  .skliis{
    width:241px;
    height: 45px;
  }
  .add{
    width:286px;
    height: 45px;
    display: flex;
    align-items: center;
  }
  button{
    background-color:#2444B5;
        height: 45px;
        width: 45px;
    
  }
  .showskill{
    display: flex;
    align-items: center;
  }
  p{
    width:234px;
    height:25px;
    background-color: #DDE3EB;
  }
  .remove{
    width:16px;
    height:16px;
  }
  .descri{
    width:286px;
    height:105px
  }
  .experience{
    display: flex;
    gap: 25px;
    flex-direction: column;
  }

</style>