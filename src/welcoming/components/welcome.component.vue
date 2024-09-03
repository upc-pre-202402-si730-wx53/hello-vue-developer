<script>
import { Developer } from "@/welcoming/model/developer.entity.js";
export default {
  name: "welcome",
  props: {
    firstName: String,
    lastName: String
  },
  methods:{
    getDeveloperName(){
      let developer = new Developer(this.firstName, this.lastName);
      return developer.fullName;
    }
  }
}
</script>

<template>
  <div>
    <h1>Welcome {{ getDeveloperName() }}. Now you are a Vue Developer.</h1>
  </div>
</template>

<style scoped>

</style>