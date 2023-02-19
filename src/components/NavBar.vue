<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>
<template>
  <!-- Här lägger ni en navbar och istället för href så använder ni RouterLink -->
  <!-- <ul>
    <li>
      <RouterLink to="/">Hem</RouterLink>
    </li>
    <li>
      <RouterLink to="/about">About</RouterLink>
    </li>
  </ul> -->
  <div class="title">
    <!-- <a class="navbar-brand" href="#">Market</a> -->
    <RouterLink class="navbar-brand" to="/">Baby Shop</RouterLink>
  </div>
  <div class="collapse" id="navbarToggleExternalContent">
    <div class="bg-dark p-7" id="textNavBar">
      <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
        <li class="nav-item">
          <!-- <a class="nav-link active" aria-current="page" href="#">Home</a> -->
          <RouterLink class="nav-link active" to="/"><i class="fa fa-fw fa-home"></i>Home</RouterLink>
        </li>
        <li class="nav-item">
          <RouterLink class="nav-link" to="/shoplist">Shop list</RouterLink>
        </li>
        <li class="nav-item">
          <!-- <a class="nav-link" href="#">Link</a> -->
          <RouterLink class="nav-link" to="/login"><i class="fa fa-fw fa-user"></i>Login</RouterLink>
        </li>
      </ul>
    </div>
  </div>
  <nav class="navbar navbar-dark bg-dark">
    <div class="container-fluid">
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarToggleExternalContent"
        aria-controls="navbarToggleExternalContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
    </div>
  </nav>
  <RouterView />
</template>

<style scoped>
.title {
  color: rgba(255, 255, 255, 0.767);
  background-color: #212529;
  height: 10vh;
  display: flex;
  justify-content: center;
  font-size: 40px;
}
#textNavBar {
  color: rgba(255, 255, 255, 0.767);
  font-weight: 500;
}
.navbar-brand {
  height: 5vh;
}
</style>
