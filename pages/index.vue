<template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-ig-6">
        <nuxt-link to="/PERPUSTAKAAN DIGITAL/tambah">
          <div class="card bg-PERPUSTAKAAN DIGITAL rounded-5">
            <div class="card-body">
              <h2>PERPUSTAKAAN DIGITAL</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
      <div class="col-lg-6">
        <nuxt-link to="cari buku">
          <div class="card bg-cari buku rounded-5">
            <div class="card-body">
              <h2>cari buku</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
  <div class="col-lg-6">
    <nuxt-link to="pengunjung">
      <div class="card bg-pengunjung rounded-5">
        <div class="card-body">
          <h2>pengunjung</h2>
        </div>
      </div>
    </nuxt-link>
  </div>
</template>




<style scoped>
.card {
  height: 230px;
  box-shadow: 1px 1px 10px #73a3c6;
}

h2 {
  background-image: url('../assets/img/bg-home-PERPUSTAKAAN DIGITAL.jpeg');
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}

.card.bg-cari buku {
  background: url('../assets/img/bg-home-cari buku.jpg') no-repeat center center;
  background-size: cover;
}
</style>