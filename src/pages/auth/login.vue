<template>
  <div>
    <h1>Login</h1>
    <form @submit.prevent="login">
      <div>
        <label for="username">Username: </label>
        <input id="username" type="text" v-model="username" required />
      </div>
      <div>
        <label for="password">Password: </label>
        <input id="password" type="password" v-model="password" required />
      </div>
      <button type="submit">Log in</button>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    login() {
      const user = {
        username: this.username,
        password: this.password,
      };
      // Do something with user credentials, like sending to an API endpoint for authentication
      // Redirect user to dashboard or display error message based on response data
    },
  },
};
</script>

<!-- This example uses Vue.js's two-way data binding to bind the input values to the component's data properties. It also uses the  v-model  directive to automatically update the data properties as the user types in the input fields. 
 
The  @submit.prevent  directive prevents the form from submitting the traditional way and instead calls the  login  method when the user clicks the "Log in" button. In the  login  method, you can perform any necessary login logic, such as sending the user's credentials to an API endpoint for authentication. Once the authentication is successful, you can redirect the user to the dashboard or display an error message if the authentication fails. -->
