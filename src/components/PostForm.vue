<script setup>
import {getCookie} from "@/main";

function postEmployee(e) {
  e.preventDefault();
  let headers = new Headers();
  headers.append('Authorization', `Bearer ${getCookie('jwt')}`);
  headers.append('Content-Type', 'application/json')
  const formData = new FormData(e.target);
  const plainFormData = Object.fromEntries(formData.entries());
  const jsonFormData = JSON.stringify(plainFormData);
  const url = `${location}api/employee`;
  fetch(url, {
    method: 'POST',
    mode: 'cors',
    headers: headers,
    body: jsonFormData
  })
}
</script>
<template>
  <form @submit="postEmployee">
    <input name="firstName" type="text" placeholder="First Name"><br>
    <input name="lastName" type="text" placeholder="Last Name"><br>
    <input name="age" type="number" placeholder="Age"><br>
    <input name="weight" type="number" placeholder="Weight"><br>
    <input name="height" type="number" placeholder="Height"><br>
    <input name="sex" type="text" placeholder="Sex"><br>
    <input name="departmentName" type="text" placeholder="Department Name"><br>
    <input name="personalCode" type="number" placeholder="Personal Code"><br>
    <input type="submit">
  </form>
</template>
