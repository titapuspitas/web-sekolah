<template>
  <div class="header fixed-top">
    <div class="h-text">
      <div class="t-judul">
        <h5>SMKN 4 TASIKMALAYA</h5>
      </div>
      <!-- Navbar -->
      <nav class="navbar navbar-expand-lg">
        <div class="container-fluid">
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNavDropdown">
            <ul class="navbar-nav">
              <li class="nav-item">
                <nuxt-link to="../" class="nav-link active" aria-current="page" href="#" style="color: white;">Beranda</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to="./profil" class="nav-link active" aria-current="page" href="#" style="color: white;">Profil</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to="./ekstra" class="nav-link active" aria-current="page" href="#" style="color: white;">Ekstrakulikuler</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to="./galeri" class="nav-link active" aria-current="page" href="#" style="color: white;">Galeri</nuxt-link>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </div>
  </div>
</template>

<style scoped>
.header {
  position: fixed; 
  top: 0;
  left: 0;
  z-index: 1000; 
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: blue;
  color: white;
  width: 100%; 
  height: 100px; 
  padding: 0;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); 
}
.h-text {
  flex: 1;
  line-height: 1.2;
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-left: 20px;
}

.t-judul h5 {
  margin: 0;
  font-size: 20px;
  font-weight: 700;
  font-family: Inria Serif;
  text-transform: uppercase;
  padding-right: 20px;
}

.navbar {
  margin-left: 500px;
}

body {
  margin-top: 15vh; 
}

.navbar-nav {
  position: relative; 
  z-index: 1100; 
}


.carousel-inner img {
  width: 100%;
  height: auto;
}
</style>