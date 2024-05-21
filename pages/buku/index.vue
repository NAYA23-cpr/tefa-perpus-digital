<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">CARI BUKU</h2>

        <div class="my-3">
          <div class="row d-flex">
            <div class="col">
              <form class="input-group flex-nowrap rounded-5">
                <span class="input-group-text"><img src="~/assets/img/img-cari.png" alt="" class="img-cari"
                    aria-label="Search" aria-describedby="search-addon"></span>
                <input type="search" class="form-control" placeholder="cari">
              </form>
            </div>
          </div>
        </div>
        <div class="my-3 text-muted">Koleksi Buku</div>
        <div class="row">
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img src="~/assets/img/novel2.jpg" class="cover" alt="cover 1">
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <nuxt-link to="/buku/detailbuku">
              <div class="card mb-3">
                <div class="card-body">
                  <img src="~/assets/img/novel4.jpeg" class="cover" alt="cover 3">
                </div>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img src="~/assets/img/novel.png" class="cover" alt="cover 3">
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img src="~/assets/img/novel3.jpg" class="cover" alt="cover 3">
              </div>
            </div>
          </div>
          <div class="col-lg-2">
            <div class="card mb-3">
              <div class="card-body">
                <img src="~/assets/img/image 6.png" class="cover" alt="cover 3">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.card-body {
  width: 100%;
  height: 22;
  padding: 0;
}

.img-cari {
  width: 80%
}

input {
  border-left: none;
}

.input-group-text {
  width: 5%;
  background-color: white;
  border-right: none;
}

.cover {
  width: 100%;
  height: 22;
  object-fit: cover;
  object-position: 0 30;
}
</style>
