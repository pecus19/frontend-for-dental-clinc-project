<script setup>
import {getCookie} from "@/main";

function deleteEmployee(e) {
  e.preventDefault();
  let headers = new Headers();
  headers.append('Authorization', `Bearer ${getCookie('jwt')}`);
  const formData = new FormData(e.target);
  const employeeId = formData.get('id');
  const url = `${location}api/employee?`;
  let params = new URLSearchParams({
    id: employeeId
  }).toString();
  fetch(url + params, {
    method: 'DELETE',
    headers: headers,
    mode: 'cors',
  }).then((response) => response.text())
      .then((data) => alert(data));
}
</script>
<template>
  <form @submit="deleteEmployee">
    <input name="id" type="number" placeholder="ID"><br>
    <input type="submit">
  </form>
</template>
