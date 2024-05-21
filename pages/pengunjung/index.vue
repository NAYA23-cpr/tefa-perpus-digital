<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text center my-4">RIWAYAT KUNJUNGAN</h2>
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
        <div class="my-3 text-muted">menampilkan 1 dari 1</div>
        <table class="table">
          <thead>
            <tr>
              <td>NO</td>
              <td>NAMA</td>
              <td>KEANGGOTAAN</td>
              <td>KEPERLUAN</td>
              <td>TANGGAL</td>
            </tr>
          </thead>

          <body>
            <tr>
              <td>1.</td>
              <td>naya hinayatulloh</td>
              <td>siswi</td>
              <td>meminjam</td>
              <td>25 Februari 2024, 23.31.00</td>
            </tr>
          </body>
        </table>
      </div>
    </div>
  </div>
  <div class="button float-end">
    <button type="submit" class="btn btn-lg rounde-5 text-blue">kembali</button>
    <nuxt-link to="/buku">
      <button type="submit" class="btn btn-lg rounde-5 text-blue">cari buku</button>
    </nuxt-link>
  </div>
</template>

<style scoped>
.btn {
  background-color: #5EAFB5;
  margin-right: 2rem;
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
</style>
