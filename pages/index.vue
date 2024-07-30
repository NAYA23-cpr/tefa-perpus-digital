<template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung/tambah" style="text-decoration:none;">
          <div class="card bg-cari buku rounded-5">
            <div class="card-body">
              <h2 class="text-white">Pengunjung</h2>
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="col-lg-6">
        <nuxt-link to="/buku" style="text-decoration: none;">
          <div class="card bg-pengunjung rounded-5">
            <div class="card-body">
              <h2 class="text-white">Buku</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>




<style scoped>
.card {
  height: 100vh;
  box-shadow: 50px 10px 200px;
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}

.card.bg-pengunjung {
  background-image: url('../assets/img/bg-home.jpg');
}

.card.bg-cari {
  background: url('../assets/img/bg-home-kunjungan.jpeg');
}

h2 {
  margin-top: 50%;
  text-align: center;
}
</style>
