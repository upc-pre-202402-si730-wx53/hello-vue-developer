<script>
import Welcome from "@/welcoming/components/welcome.component.vue";
import RegisterDeveloper from "@/welcoming/components/register-developer.component.vue";

export default {
  name: "App",
  components: {
    Welcome,
    RegisterDeveloper,
  },
  data(){
    return {
        firstName: "",
        lastName: "",
    }
  },
  methods: {
    onDeveloperRegistered(_developer){
      console.log("Developer registered: ", _developer);
      this.firstName = _developer.firstName;
      this.lastName = _developer.lastName;
    }
  }
};
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <register-developer @developer-registered="onDeveloperRegistered" />
      <br>
      <br>
      <br>
      <welcome :first-name="firstName" :last-name="lastName" />
    </div>
  </header>

  <main>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
