<script setup>

import {setCookie} from "@/main";

function postLogIn(e) {
  e.preventDefault();
  const formData = new FormData(e.target);
  const plainFormData = Object.fromEntries(formData.entries());
  const jsonFormData = JSON.stringify(plainFormData);
  const url = `${location}api/public/account/token`;
  fetch(url, {
    method: 'POST',
    headers: {
      "Content-Type": "application/json",
    },
    body: jsonFormData
  }).then((response) => response.text())
      .then((token) => setCookie("jwt", token, 10));
}
</script>
<template id="login-form">
  <form @submit="postLogIn">
    <h2>Login</h2>
    <h3>
      <button onclick="document.getElementById('id01').style.display='block'" style="width:auto;">Login</button>
    </h3>
    <div id="id01" class="modal">
      <div class="modal-content animate">
        <div class="imgcontainer">
        <span class="close" onclick="window.location.reload();"
              title="Close Modal">&times;</span>
        </div>
        <div class="container">
          <label for="email"><b>Email</b></label>
          <input type="login" placeholder="Enter email" name="email" required>
          <label for="psw"><b>Password</b></label>
          <input type="password" placeholder="Enter Password" name="plainPassword" required>
          <button type="submit">Login</button>
        </div>
        <div class="container" style="background-color:#f1f1f1">
          <button type="button" onclick="window.location.reload();" class="cancelbtn">Cancel
          </button>
        </div>
      </div>
    </div>
  </form>
</template>
<style>
body {
  font-family: Arial, Helvetica, sans-serif;
}

/* Full-width input fields */
input[type=login], input[type=password] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  box-sizing: border-box;
}

h2 {
  padding-top: 20px;
  padding-left: 100px;
}

h3 {
  padding-left: 100px;
}

/* Set a style for all buttons */
button {
  background-color: #04AA6D;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  cursor: pointer;
  width: 100%;
}

button:hover {
  opacity: 0.8;
}


/* Extra styles for the cancel button */
.cancelbtn {
  width: auto;
  padding: 10px 18px;
  background-color: #f44336;
}

/* Center the image and position the close button */
.imgcontainer {
  text-align: center;
  margin: 24px 0 12px 0;
  position: relative;
}

.container {
  padding: 16px;
}

/* The Modal (background) */
.modal {
  display: none; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0, 0, 0); /* Fallback color */
  background-color: rgba(0, 0, 0, 0.4); /* Black w/ opacity */
  padding-top: 60px;
}

/* Modal Content/Box */
.modal-content {
  background-color: #fefefe;
  margin: 5% auto 15% auto; /* 5% from the top, 15% from the bottom and centered */
  border: 1px solid #888;
  width: 80%; /* Could be more or less, depending on screen size */
}

/* The Close Button (x) */
.close {
  position: absolute;
  right: 25px;
  top: 0;
  color: #000;
  font-size: 35px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: red;
  cursor: pointer;
}

/* Add Zoom Animation */
.animate {
  -webkit-animation: animatezoom 0.6s;
  animation: animatezoom 0.6s
}

@keyframes animatezoom {
  from {
    transform: scale(0)
  }
  to {
    transform: scale(1)
  }
}

@keyframes animatezoom {
  from {
    transform: scale(0)
  }
  to {
    transform: scale(1)
  }
}

/* Change styles for span and cancel button on extra small screens */
@media screen and (max-width: 300px) {
  span.psw {
    display: block;
    float: none;
  }

  .cancelbtn {
    width: 100%;
  }
}

* {
  box-sizing: border-box;
}

html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
  background-color: azure;
}


input[type="text_email"],
input[type="password"] {
  width: 100%;
  height: 40px;
  border-bottom: 1px solid #aaaaaa;
}
</style>
