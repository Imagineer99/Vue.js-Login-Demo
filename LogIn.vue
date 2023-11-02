<template>
  <div class="login-container">
    <div class="login-box">
      <h1 class="header">Login System</h1>
      <transition name="fade">
        <div v-if="!loggedIn" class="login-form">
          <input v-model="username" placeholder="Username">
          <input v-model="password" type="password" placeholder="Password"> <!-- Password input -->
          <button @click="login">Log In</button>
        </div>
      </transition>
      <transition name="fade">
        <h1 v-if="loggedIn" class="welcome-message">Welcome, {{ username }}</h1>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '', // Added password data property
      loggedIn: false,
    };
  },
  methods: {
    login() {
      // Simulate a login process (you would replace this with your authentication logic)
      if (this.username && this.password) {
        this.loggedIn = true;
      }
    },
  },
};
</script>


<style>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  
  height: 100vh;
  background-color: #f0f0f0;
}
.login-form {
    margin-top: 0px;
    display: inline-grid;
}
.login-box {
  text-align: center;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #fff;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}

.header {
  font-size: 24px;
  color: #333;
}

.login-form {
  margin-top: 0px;
  
}
input, button {
  padding: 8px;
  margin: 4px;
  border: none;
}

input {
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  background-color: #0073e6;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.welcome-message {
  font-size: 20px;
  margin-top: 20px;
  color: #0073e6;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.66s;
}

.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>


<!--
  WARNING: This code is a basic example for educational and prototyping purposes.
  It does not include real authentication logic and should not be used in production without proper security measures.
-->

