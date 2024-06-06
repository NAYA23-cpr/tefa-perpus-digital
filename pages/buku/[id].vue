<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">Rincian buku</h2>
        <div class="my-3">
    
        </div>
      </div>
    </div>
    <div class="row pt-4">
      <div class="col-md-3">
        <img :src="buku?.cover" alt="cover" style="width: 300px;">
      </div>
      <div class="col-md-6">
        <ul>
          <li>Judul buku: {{ buku?.judul }}</li>
          <li>Tahun terbit: {{ buku.tahun_terbit }} </li>
          <li>Kategori: {{ buku?.kategori?.nama }} </li>
          <!-- <li>Penulis: {{ buku?.penulis }} </li> -->
          <li>Rak: {{ buku?.rak }} </li>
          <li>Penerbit: {{ buku?.penerbit }} </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()
const route = useRoute()
const buku = ref([])
const getbookById = async () => {
  const { data, error } = await supabase.from('buku').select(`*, kategori(*)`)
    .eq('id', route.params.id)
  if (data) buku.value = data[0]
}

onMounted(() => {
  getbookById()
})
</script>

<style scoped>
ul {
  list-style-type: none;
}

li {
  font-size: 20px;
}
</style>