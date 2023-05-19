<template>
  <div>
    <h2>Register</h2>
    <form @submit.prevent="submitForm">
      <div>
        <label for="username">Username</label>
        <input type="text" id="username" v-model.trim="username" />
        <p v-if="$v.username.$error">Username is required</p>
      </div>
      <div>
        <label for="password">Password</label>
        <input type="password" id="password" v-model.trim="password" />
        <p v-if="$v.password.$error">Password is required</p>
      </div>
      <div>
        <label for="email">Email</label>
        <input type="email" id="email" v-model.trim="email" />
        <p v-if="$v.email.$error">Please enter a valid email</p>
      </div>
      <button type="submit">Register</button>
    </form>
  </div>
</template>
<script>
import { required, email } from 'vuelidate/lib/validators'
export default {
  data() {
    return {
      username: '',
      password: '',
      email: ''
    }
  },
  validations: {
    username: { required },
    password: { required },
    email: { required, email }
  },
  methods: {
    submitForm() {
      // send form data to server here
    }
  }
}
</script>