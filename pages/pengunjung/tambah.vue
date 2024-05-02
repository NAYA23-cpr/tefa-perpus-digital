<template>
  <div class="container-fluid">
    <div class="cil-ig-12">
      <h2 class="text-center my-4">ISI DATA PENGUNJUNG</h2>
      <form>
        <div class="mb-3">
          <input type="text" class="form-control-lg rounded-5"placeholder="NAMA...">
        </div>
        <div class="mb-3">
          <select class="form-control-lg form-select rounded-5">
            <option value="">KEANGGOTAAN</option>
            <option value="siswa">siswa</option>
            <option value="guru">guru</option>
            <option value="staf">staf</option>
            <option value="umum">umum</option>
          </select>
        </div>
        <div class="mb-3">
          <div class="row">
            <div class="col-md-4">
              <select class="form-control form-control-lg form-select rounded-5 mb-2">
                <option value="">KELAS</option>
            <option value="X">X</option>
            <option value="XI">XI</option>
            <option value="XII">XII</option>
              </select>
            </div>
            <div class="mb-4">
              <select class="form-control form-control-lg form-select rounded-5 mb-2">
                <option value="">JURUSAN</option>
            <option value="PPLG">PPLG</option>
            <option value="TKJT">TKJT</option>
            <option value="TSM">TSM</option>
            <option value="TOI">TOI</option>
            <option value="DKV">DKV</option>
          </select>
            </div>
            <div class="mb-3">
              <select class="form-control form-control-lg form-select rounded-5">
                <option value="">KEPERLUAN</option>
            <option value="baca">Baca buku</option>
            <option value="pinjam">Pinjam buku</option>
            <option value="kembalikan">Kembalikan buku</option>
          </select>
            </div>
            <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">SUBMIT</button>
        </div>
        </div>
      </form>
    </div>
  </div>
</template>

