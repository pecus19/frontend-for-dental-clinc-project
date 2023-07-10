<script setup>
import {getCookie} from "@/main";

function getEmployee(e) {
  let headers = new Headers();
  headers.append('Authorization', `Bearer ${getCookie('jwt')}`);

  e.preventDefault();
  const url = `${location}api/employee`;
  fetch(url, {
    method: 'GET',
    headers: headers,
    mode: 'cors',
  }).then((response) => response.json())
      .then((data) => alert(JSON.stringify(data)));
}
</script>
<template>
  <form @submit="getEmployee">
    <input type="submit">
  </form>
</template>
