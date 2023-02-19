<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>
<template>
<!-- Footer -->
<footer id="all-footer" class="bg-dark text-center text-white">
  <!-- Grid container -->
  <div class="container p-4">
    <!-- Section: Social media -->
    <section class="mb-4">
      <!-- Facebook -->
      <a class="btn btn-outline-light btn-floating m-1" href="#!" role="button"
        ><i class="fab fa-facebook-f"></i
      ></a>

      <!-- Twitter -->
      <a class="btn btn-outline-light btn-floating m-1" href="#!" role="button"
        ><i class="fab fa-twitter"></i
      ></a>

      <!-- Instagram -->
      <a class="btn btn-outline-light btn-floating m-1" href="#!" role="button"
        ><i class="fab fa-instagram"></i
      ></a>

    </section>
    <!-- Section: Social media -->

    <!-- Section: Form -->
    <section class="">
      <form @submit="onSubmit" action="">
        <!--Grid row-->
        <div class="row d-flex justify-content-center">
          <!--Grid column-->
          <div class="col-auto">
            <p class="pt-2">
              <strong>Sign up for our newsletter</strong>
            </p>
          </div>
          <!--Grid column-->

          <!--Grid column-->
          <div class="col-md-5 col-12">
            <!-- Email input -->
            <div class="form-outline form-white mb-4">
              <input type="email" v-model="userName" id="form5Example21" class="form-control"  />
              <label id="massage" v-if="message !== null" class="form-label" for="form5Example21">{{ message }}</label>
            </div>
          </div>
          <!--Grid column-->

          <!--Grid column-->
          <div class="col-auto">
            <!-- Submit button -->
            <input type="submit" :disabled="userName.length === 0" class="btn btn-outline-light mb-4" value="Subscribe" />
            <!-- <button type="submit" class="btn btn-outline-light mb-4">
              Subscribe
            </button> -->
          </div>
          <!--Grid column-->
        </div>
        <!--Grid row-->
      </form>
    </section>
    <!-- Section: Form -->

    <!-- Section: Text -->
    <section class="mb-4">
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt distinctio earum
        repellat quaerat voluptatibus placeat nam, commodi optio pariatur est quia magnam
        eum harum corrupti dicta, aliquam sequi voluptate quas.
      </p>
    </section>
    <!-- Section: Text -->

  </div>
  <!-- Grid container -->

  <!-- Copyright -->
  <div class="text-center p-3" style="background-color: rgba(0, 0, 0, 0.2);">
    © 2020 Copyright:
    <RouterLink class="navbar-brand" to="/">BabyShop.com</RouterLink>
    <!-- <a class="text-white" href="https://BabyShop.com/">BabyShop.se</a> -->
  </div>
  <!-- Copyright -->
</footer>
<!-- Footer -->

  <RouterView />
</template>


<script>
export default {
  data() {
    return {
        message : null,
        userName:""
    };
  },

  methods: {
    onSubmit(event) {
        this.message =`Thanks for subscribing  ${this.userName}`
       event.preventDefault()
    },
  },

};
</script>

<style scoped>

#all-footer{
    margin-top: 30vh;
}

#massage{
    color: red;
    font-weight: 600;
    font-size: 20px;
}
</style>
