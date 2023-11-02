<template>
  <div class="login-container">
    <div class="login-box">
      <h1 class="header">Login System</h1>
      <transition name="fade">
        <div v-if="!loggedIn" class="login-form">
          <input v-model="username" placeholder="Username">
          <input v-model="password" type="password" placeholder="Password">
          <button @click="login">Log In</button>
        </div>
      </transition>
      <transition name="fade">
        <div v-if="loggedIn" class="welcome-message">
          <h1>Welcome, {{ username }}</h1>
          <button @click="logout">Log Out</button>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
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
    logout() {
      this.loggedIn = false;
      this.username = '';
      this.password = '';
    },
  },
};
</script>

<style>

:root {
  --primary-color: #0073e6;
  --bg-color: #f0f0f0;

  --input-bg: #fff;
  --input-border: #ccc;
  --input-hover: #f2f2f2;

  --btn-bg: var(--primary-color);
  --btn-color: #fff;
  --btn-hover: #0056b3;
}

*, *::before, *::after {
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  font-size: 16px;
  line-height: 1.5;
  background-color: var(--bg-color);
}

.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.login-box {
  max-width: 400px;
  height: 300px;
  padding: 20px;
  overflow: hidden;
  text-align: center;
  border: 1px solid var(--input-border);
  border-radius: 8px;
  background-color: var(--input-bg);
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

.header {
  font-size: 1.5rem;
  font-weight: 600; 
  margin-bottom: 1rem;
  color: var(--primary-color);
}

.login-form {
  display: flex;
  flex-direction: column;
}

input,
button {
  padding: 0.75rem 1rem;
  border-radius: 4px; 
}

input {
  margin-bottom: 1rem;
  border: 1px solid var(--input-border);
  background-color: #fff;
  transition: border-color 0.2s, background-color 0.2s;
}

input:focus {
  border-color: var(--primary-color);
  background-color: var(--input-hover);
  outline: none;
}

input::placeholder {
  color: #aaa;
}

button {
  width: 100%;
  border: none;
  background-color: var(--btn-bg);
  color: var(--btn-color);
  transition: background-color 0.2s;
}

button:hover {
  background-color: var(--btn-hover);
}



button:hover::after {
  margin-left: 1rem; 
}

.welcome-message {
  font-size: 1.25rem;
  margin-top: 1rem;
  color: var(--primary-color);
}
.login-box {
    max-width: 400px;
    height: 300px;
    padding: 9px !important; 
    overflow: hidden;
    text-align: center;
    border: 1px solid var(--input-border);
    border-radius: 8px;
    background-color: var(--input-bg);
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}
/* Animations */

@keyframes slideIn {
  0% {
    max-height: 0;
  }
  
  100% {
    max-height: 300px;
  }
}

.fade-enter-active {
  animation: slideIn 0.5s cubic-bezier(0.645, 0.045, 0.355, 1);  
}

@keyframes slideOut {
  0% {
    max-height: 300px;
  }

  100% {
    max-height: 0;
  }
}

.fade-leave-active {
  animation: slideOut 0.8s cubic-bezier(0.645, 0.045, 0.355, 1);
}
/* Animations */

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}

.fade-enter-active {
  animation: fadeIn 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
}

.fade-leave-active {
  animation: fadeOut 0.3s cubic-bezier(0.645, 0.045, 0.355, 1); 
}
/* Responsive */

@media (max-width: 576px) {
  .login-box {
    padding: 1.5rem; 
  }

  input,
  button {
    width: 100%;
  }
}
</style>
