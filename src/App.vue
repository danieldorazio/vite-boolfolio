<script>
export default {
  data() {
    return {};
  },
}


</script>

<template>
  <header>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <router-link :to="{ name: 'home' }" class="nav-link active">Home</router-link>
            </li>
            <li class="nav-item">
              <router-link :to="{ name: 'about'}" class="nav-link active">About</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>


  <router-view></router-view>
</template>

<style lang="scss">
@use "./style/general.scss" as *;
</style>
