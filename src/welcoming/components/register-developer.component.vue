<script>

export default {
  name: "register-developer",
  data(){
    return {
      firstName: "",
      lastName: ""
    }
  },
  methods:{
    myOnSubmit(){
      console.log("Registering Developer");
      console.log(this.firstName, this.lastName);
      this.$emit("developer-registered", {firstName: this.firstName, lastName: this.lastName});
    }
  }

}

</script>

<template>
  <div>
    <h2>New Developer</h2>
    <div>
      <form @submit.prevent="myOnSubmit">
        <div>
          <label for="firstName">First Name</label>
          <input type="text" id="firstName" v-model="firstName" />
        </div>
        <div>
          <label for="lastName">Last Name</label>
          <input type="text" id="lastName" v-model="lastName" />
        </div>
        <div>
          <button type="submit">Register</button>
        </div>
      </form>
    </div>
  </div>
  
</template>

<style scoped>

</style>