<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text center my-4">RIWAYAT KUNJUNGAN</h2>
        <div class="my-3">
          <div class="row d-flex">
            <div class="col">

              <form @submit.prevent="getBooks" class="input-group flex-nowrap rounded-5">
                <span class="input-group-text"><img src="~/assets/img/img-cari.png" alt="" class="img-cari"
                    aria-label="Search" aria-describedby="search-addon"></span>
                <input v-model="keyword" type="search" class="form-control" placeholder="cari">
              </form>
            </div>
          </div>
        </div>
        <div class="my-3 text-muted">Menampilkan 1 dari 1</div>
        <table class="table">
          <thead>
            <tr>
              <td>NO</td>
              <td>NAMA</td>
              <td>KEANGGOTAAN</td>
              <td>KELAS LENGKAP</td>
              <td>TANGGAL</td>
              <td>KEPERLUAN</td>
            </tr>
          </thead>

          <tbody>
            <tr v-for="(visitor, i) in pengunjungFiltered" :key="i">
              <td>{{ i + 1 }}.</td>
              <td>{{ visitor.Nama }}</td>
              <td>{{ visitor.Keanggotaan.Nama }}</td>
              <td>{{ visitor.Tingkat }} {{ visitor.Jurusan }} {{ visitor.Kelas }}</td>
              <td>{{ visitor.Tanggal }}</td>
              <td>{{ visitor.Keperluan.nama }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
  <div class="button float-end">
    <nuxt-link to="/pengunjung/tambah">
      <button type="submit" class="btn btn-lg rounde-5 text-blue">kembali</button>
    </nuxt-link>
    <nuxt-link to="/buku">
      <button class="btn btn-lg rounde-5 text-blue">cari buku</button>
    </nuxt-link>
  </div>
</template>

<style scoped>
.btn {
  background-color: #5EAFB5;
  margin-right: 2rem;
}

.img-cari {
  width: 80%;
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
<script setup>
const supabase = useSupabaseClient()
const keyword = ref('')
const visitors = ref([])

const getPengunjung = async () => {
  const { data, error } = await supabase.from('Pengunjung')
    .select(`*, Keanggotaan(*), Keperluan(*)`)
  if (data) visitors.value = data

}

// const getBooks = async () => {
//     const {data, error} = await supabase.from('buku')
//     .select(`*,kategori(*)`)
//     .ilike('judul', `%${keyword.value}%`)
//     if (data) books.value = data
// }

const pengunjungFiltered = computed(() => {
  return visitors.value.filter((b) => {
    return (
      b.Nama?.toLowerCase().includes(keyword.value?.toLowerCase()) ||
      b.Keanggotaan.Nama?.toLowerCase().includes(keyword.value?.toLowerCase())
    )
  })
})
onMounted(() => {
  getPengunjung()
})
</script>
