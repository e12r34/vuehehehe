<template>
  <div class="absolute top-32 left-1/4">
    <div id="container" :class="isActive ? 'active' : 'close'">
      <div class="login">
        <div class="content">
          <h1>Log In</h1>
          <form>
            <input type="email" placeholder="email">
            <input type="password" placeholder="password">
            <div>
              <label class="remember" for="remember">
                <input type="checkbox" id="remember" checked /><span>Remember me</span>
              </label>
              <span class="forget"><a href="#">Forgot password?</a></span>
              <span class="clearfix"></span>
            </div>
            <button @click.prevent="login">Log In</button>
          </form>
          <span class="loginwith">Or Connect with</span>
          <div>
            <a href="https://www.facebook.com/emin.qasimovdia"><i class="fab fa-facebook"></i></a>
            <a href="https://www.twitter.com/webkoder"><i class="fab fa-twitter"></i></a>
            <a href="https://www.github.com/eminqasimov"><i class="fab fa-github"></i></a>
            <a href="https://www.linkedin.com/in/eminqasimov/"><i class="fab fa-linkedin"></i></a>
          </div>
          <span class="copy">&copy; {{ currentYear }}</span>
        </div>
      </div>
      <div class="page front">
        <div class="content">
          <svg xmlns="http://www.w3.org/2000/svg" width="96" height="96" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M16 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2" />
            <circle cx="8.5" cy="7" r="4" />
            <line x1="20" y1="8" x2="20" y2="14" />
            <line x1="23" y1="11" x2="17" y2="11" />
          </svg>
          <h1>Hello, friend!</h1>
          <p>Enter your personal details and start a journey with us</p>
          <button @click="toggleForm" type="" id="register">Register <i class="fas fa-arrow-circle-right"></i></button>
        </div>
      </div>
      <div class="page back">
        <div class="content">
          <svg xmlns="http://www.w3.org/2000/svg" width="96" height="96" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M15 3h4a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2h-4" />
            <polyline points="10 17 15 12 10 7" />
            <line x1="15" y1="12" x2="3" y2="12" />
          </svg>
          <h1>Welcome Back!</h1>
          <p>To stay connected with us, please log in with your personal info</p>
          <button @click="toggleForm" type="" id="login"><i class="fas fa-sign-in-alt"></i> Log In</button>
        </div>
      </div>
      <div class="register">
        <div class="content">
          <h1>Sign Up</h1>
          <div>
            <a><i class="fab fa-facebook"></i></a>
            <a><i class="fab fa-twitter"></i></a>
            <a><i class="fab fa-github"></i></a>
            <a><i class="fab fa-linkedin"></i></a>
          </div>
          <span class="loginwith">Or use email</span>
          <form>
            <input type="text" placeholder="name">
            <input type="email" placeholder="email">
            <input type="password" placeholder="password">
            <label class="remember" for="terms">
              <input type="checkbox" id="terms" /><span>I accept terms</span>
            </label>
            <span class="clearfix"></span>
            <button @click.prevent="submit">Submit</button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

import { ref } from 'vue'
const isActive = ref(false)

function toggleForm() {
  
  isActive.value=!isActive.value
}

</script>
  
<style>
@import url("https://fonts.googleapis.com/css?family=Montserrat:400,700");
:root {
  --main-bg-color: #9C27B0;
}

*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: inherit;
}

html {
  height: 100%;
  box-sizing: border-box;
  font-family: Montserrat, sans-serif;
  -webkit-font-smoothing: antialiased;
  font-weight: 400;
}

body {
  height: 100%;
  font-size: 65.2%;
  background: #e9ebee;
  color: #1d2129;
  display: flex;
  perspective: 1600px;
}

.login-form-version {
  position: absolute;
  bottom: 1em;
  right: 2em;
  border-radius: 4em;
  background: #ff4b2b;
  color: #fff;
  font-size: 1em;
  font-weight: bold;
  padding: 0.8em 2em;
  letter-spacing: 0.1em;
  transition: transform 80ms ease-in;
}

h1 {
  font-weight: 700;
  font-size: 3.5em;
  text-align: center;
}

form input {
  background: #eee;
  border: none;
  padding: 12px 15px;
  margin: 0.8em 0;
  width: 100%;
  font-size: 1.4em;
}
form input:focus {
  outline: 1px solid var(--main-bg-color);
}

span {
  color: #333;
  font-size: 1.4em;
  display: inline-block;
  margin: 15px auto;
  font-weight: 100;
  -webkit-user-select: none;
     -moz-user-select: none;
          user-select: none;
}

label {
  float: left;
  font-size: 1.4em;
  display: inline-block;
  -webkit-user-select: none;
     -moz-user-select: none;
          user-select: none;
}
label:hover {
  cursor: pointer;
}
label span {
  font-size: inherit;
  line-height: 1em;
}
label span::before {
  content: "";
  width: 1em;
  height: 1em;
  display: inline-block;
  border: 2px solid #aaa;
  vertical-align: bottom;
  transition: all 0.1s ease-in-out;
  margin-right: 0.2em;
  transform: scale(0.99);
}

input[type=checkbox] {
  border: 0;
  clip: rect(0 0 0 0);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  width: 1px;
}
input[type=checkbox]:checked + span::before {
  border-color: #fafafa;
  box-shadow: 0 0 0 2px var(--main-bg-color);
  background: var(--main-bg-color);
  transform: scale(0.8);
}
input[type=checkbox]:focus + span {
  text-decoration: underline;
}
input[type=checkbox]:checked + span {
  text-decoration: none;
}

span.login-form-forget {
  float: right;
}

span.login-form-clearfix {
  clear: both;
  display: table;
}

span.login-form-loginwith {
  display: block;
  width: 100%;
  margin-top: 1em;
  white-space: nowrap;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}
span.login-form-loginwith::before {
  content: "";
  display: inline-block;
  width: 42%;
  border-bottom: 1px solid #aaa;
  vertical-align: middle;
  margin-right: 5%;
}
span.login-form-loginwith::after {
  content: "";
  display: inline-block;
  width: 45%;
  border-bottom: 1px solid #aaa;
  vertical-align: middle;
  margin-left: 5%;
}

span.login-form-copy {
  display: block;
  font-size: 1em;
  margin-top: auto;
}

button {
  display: block;
  margin: 1em auto;
  border-radius: 4em;
  border: 1px solid var(--main-bg-color);
  background: var(--main-bg-color);
  color: #fff;
  font-size: 1.2em;
  font-family: Montserrat, sans-serif;
  -webkit-font-smoothing: antialiased;
  font-weight: bold;
  padding: 0.8em 2em;
  letter-spacing: 1px;
  text-transform: uppercase;
  transition: transform 80ms ease-in;
  -webkit-user-select: none;
     -moz-user-select: none;
          user-select: none;
}
button svg {
  vertical-align: middle;
}

button:hover {
  cursor: pointer;
}

button:active {
  transform: scale(0.95);
}

button:focus {
  outline: none;
}

a {
  transition: all 0.3s ease;
  cursor: pointer;
  color: #333;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

a:hover svg {
  cursor: pointer;
  transition: all 0.3s ease;
  stroke: var(--main-bg-color);
}

#container {
  width: 100%;
  max-width: 80em;
  min-width: 70.5em;
  height: 50em;
  position: relative;
  border-radius: 2em;
  transform-style: preserve-3d;
  margin: auto;
}
#container > div {
  position: absolute;
  width: 50%;
  height: 100%;
  top: 0;
}

.content {
  width: 100%;
  height: 100%;
  padding: 0 4em;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.content p {
  font-size: 1.4em;
}

.login {
  left: 0;
  border-radius: 2em 0 0 2em;
  transform-style: preserve-3d;
}
.login button {
  border-radius: 0px;
  width: 100%;
}
.login svg {
  margin: 1em;
  stroke: #999;
}
.login .content {
  background: #FAFAFA;
  border-radius: 2em 0 0 2em;
}
.login h1 {
  margin-top: auto;
}

.register {
  right: 0;
  border-radius: 0 20px 20px 0;
  transform-style: preserve-3d;
}
.register button {
  border-radius: 0px;
  width: 100%;
  margin-bottom: auto;
}
.register svg {
  margin: 1em;
  stroke: #999;
}
.register .content {
  border-radius: 0 20px 20px 0;
  background: #FAFAFA;
  padding: 0em 4em;
}

.page {
  right: 0;
  color: #fff;
  border-radius: 0 20px 20px 0;
  transform-origin: left center;
  transition: animation 1s linear;
}
.page button {
  border-color: #fff;
  background: transparent;
}

.front {
  background: linear-gradient(-45deg, var(--main-bg-color) 0%, #1d2129 100%) no-repeat 0 0/100%;
  z-index: 3;
}

.back {
  background: linear-gradient(135deg, var(--main-bg-color) 0%, #1d2129 100%) no-repeat 0 0/200%;
  z-index: 2;
}
.back .content {
  transform: rotateY(180deg);
}

.active .front {
  animation: rot-front 0.6s ease-in-out normal forwards;
}

.active .back {
  animation: rot-back 0.6s ease-in-out normal forwards;
}

.close .front {
  animation: close-rot-front 0.6s ease-in-out normal forwards;
}

.close .back {
  animation: close-rot-back 0.6s ease-in-out normal forwards;
}

@keyframes rot-front {
  from {
    transform: translateZ(2px) rotateY(0deg);
  }
  to {
    transform: translateZ(1px) rotateY(-180deg);
  }
}
@keyframes rot-back {
  from {
    transform: translateZ(1px) rotateY(0deg);
  }
  to {
    transform: translateZ(2px) rotateY(-180deg);
  }
}
@keyframes close-rot-front {
  from {
    transform: translateZ(1px) rotateY(-180deg);
  }
  to {
    transform: translateZ(2px) rotateY(0deg);
  }
}
@keyframes close-rot-back {
  from {
    transform: translateZ(2px) rotateY(-180deg);
  }
  to {
    transform: translateZ(1px) rotateY(0deg);
  }
}
.active .register .content {
  transform-origin: left center;
  animation: show-register 0.7s ease-in-out normal forwards;
}

.active .login .content {
  transform-origin: right center;
  animation: hide-login 0.7s ease-in-out normal forwards;
}

.close .register .content {
  transform-origin: left center;
  animation: hide-register 0.7s ease-in-out normal forwards;
}

.close .login .content {
  transform-origin: right center;
  animation: show-login 0.7s ease-in-out normal forwards;
}

@keyframes show-register {
  from {
    transform: rotateY(80deg);
  }
  to {
    transform: rotateY(0deg);
  }
}
@keyframes hide-login {
  from {
    transform: rotateY(0.01deg);
  }
  to {
    transform: rotateY(-80deg);
  }
}
@keyframes hide-register {
  from {
    transform: rotateY(0.01deg);
  }
  to {
    transform: rotateY(80deg);
  }
}
@keyframes show-login {
  from {
    transform: rotateY(-80deg);
  }
  to {
    transform: rotateY(0deg);
  }
}/*# sourceMappingURL=login.css.map */
</style>
  