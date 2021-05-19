<template>
  <div id="multi-input">
    <h1>Add user</h1>
    <div v-for="user in users" :key="user.id">
      <input v-model="user.name">
      <input v-model="user.email">
      <button @click="deleteUser(user.id)">delete</button>
    </div>

    <button @click="addUser">New User</button>

    <pre>
      {{users}}
    </pre>
  </div>
</template>

<script>
export default {
  name: 'multi-input',  
  data() {
      return {
        count: 1,
        users: [{id:1, name:'jaturapat', email:'umt.eng52@gmail.com'}]
      }
    },
  methods: {
    addUser:function(){      
      this.count++;
      this.users.push({id: this.count, name:'', email:''});
    },
    deleteUser: function(id){  
      this.users.splice(this.users.findIndex(e => e.id == id), 1);
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
