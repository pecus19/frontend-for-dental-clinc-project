<script setup>
import GetForm from './components/GetForm.vue'
import PostForm from './components/PostForm.vue'
import PutForm from './components/PutForm.vue'
import DeleteForm from './components/DeleteForm.vue'
import LoginForm from "./components/LoginForm.vue"
import SignUp from "./components/SignUp.vue";
import DeleteAccount from "@/components/DeleteAccount.vue";
import DeleteCookie from "@/components/DeleteCookie.vue";
</script>

<template>
  <div id="callback-services">
    <div id="get-employee">
      <span>GET Employee</span>
      <GetForm/>
    </div>
    <div id="post-employee">
      <span>POST Employee</span>
      <PostForm/>
    </div>
    <div id="put-employee">
      <span>PUT Employee</span>
      <PutForm/>
    </div>
    <div id="delete-employee">
      <span>DELETE Employee</span>
      <DeleteForm/>
    </div>
  </div>
  <div id="sign-up">
    <SignUp/>
    <div>
    </div>
    <div id="log-in">
      <LoginForm/>
    </div>
  </div>
  <div>
    <div id="delete-account">
      <DeleteAccount/>
    </div>
  </div>
  <div>
    <div id="delete-cookie">
      <DeleteCookie/>
    </div>
  </div>
</template>
<script>
</script>

<style>
#callback-services {
  width: 100%;
  display: flex;
  margin-top: 50px;
}

#callback-services > div {
  margin: 0 10px 0 10px;
  width: 100%;
}

#callback-services > #get-employee {
  background-color: #6ecaf5;
}

#callback-services > #post-employee {
  background-color: #6ecaf5;
}

#callback-services > #put-employee {
  background-color: #6ecaf5;
}

#callback-services > #delete-employee {
  background-color: #6ecaf5;
}
</style>
