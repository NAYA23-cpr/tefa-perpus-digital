<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col">
        <h2 class="text-center my-4">CARI BUKU</h2>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <form form @submit.prevent="getbooks" class="input-group flex-nowrap rounded-5">
          <span class="input-group-text"><img src="~/assets/img/img-cari.png" alt="" class="img-cari"
              aria-label="Search" aria-describedby="search-addon"></span>
          <input v-model="keyword" type="search" class="form-control" placeholder="cari">
        </form>
      </div>
    </div>
    <div class="row">
      <div class="col-lg-12">
        <div class="my-3 text-muted">Koleksi Buku</div>
      </div>
    </div>
    <div class="row">
      <div v-for="(book, i) in books" key="i" class="col-2 d-flex">
        <div class="card flex-fill mb-3">
          <nuxt-link :to="`/buku/${book.id}`">
            <div class="card-body">
              <img :src="book.cover" class="cover card-img-top" alt="cover">
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>

    <nuxt-link to="/pengunjung">
      <button type="submit" class="btn btn-lg rounde-5 text-blue float-end">Kembali</button>
    </nuxt-link>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()
const keyword = ref('')
const books = ref([])

const getbooks = async () => {
  const { data, error } = await supabase.from('buku').select('*').ilike('judul', `%${keyword.value}%`)
  if (data) books.value = data
}

onMounted(() => {
  getbooks()
})

// <from @submit.prevent="getbooks">
//   <input v-model="keyword" type="search">
// </from>
</script>

<style scoped>
.card-body {
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

/* .cover {
  width: 100%;
  object-fit: cover;
  object-position: 0 30;
} */

.btn {
  background-color: #5EAFB5;
  margin-right: 2rem;
}
</style>
