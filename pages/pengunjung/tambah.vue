<template>
  <div class="container-fluid">
    <div class="col-lg-12">
      <h2 class="text-center my-4">ISI DATA PENGUNJUNG</h2>
      <form @submit.prevent="kirimData">
        <div class="mb-3">
          <input v-model="form.Nama" type="text" class="form-control rounded-5" placeholder="NAMA...">
        </div>
        <div class="mb-3">
          <select v-model="form.Keanggotaan" class="form-control-lg form-select rounded-5">
            <option value="">Keanggotaan</option>
            <option v-for="(member, i) in members" :key="i" :value="member.id">{{ member.Nama }}</option>
          </select>
        </div>
        <div class="mb-3">
          <div class="row">
            <div class="col-md-4">
              <select v-model="form.Tingkat" class="form-control form-control-lg form-select rounded-5 mb-2">
                <option value="">Tingkat</option>
                <option value="X">X</option>
                <option value="XI">XI</option>
                <option value="XII">XII</option>
              </select>
            </div>
            <div class="col-md-4">
              <select v-model="form.Jurusan" class="form-control form-control-lg form-select rounded-5 mb-2">
                <option value="">Jurusan</option>
                <option value="PPLG">PPLG</option>
                <option value="TKJT">TKJT</option>
                <option value="TSM">TSM</option>
                <option value="TOI">TOI</option>
                <option value="DKV">DKV</option>
              </select>
            </div>
            <div class="col-md-4">
              <select v-model="form.Kelas" class="form-control form-control-lg form-select rounded-5 mb-2">
                <option value="">Kelas</option>
                <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
                <option value="4">4</option>
              </select>
            </div>
          </div>
        </div>
        <div class="mb-3">
          <select v-model="form.Keperluan" class="form-control form-control-lg form-select rounded-5">
            <option value="">Keperluan</option>
            <option v-for="(item, i) in objectives" :key="i" :value="item.id">{{ item.nama }}</option>

          </select>
        </div>
        <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">KIRIM</button>
      </form>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()
const members = ref([])
const objectives = ref([])

const form = ref({
  Nama: "",
  Keanggotaan: "",
  Tingkat: "",
  Jurusan: "",
  Kelas: "",
  Keperluan: "",
})

const kirimData = async () => {
  const { error } = await supabase.from('Pengunjung').insert([form.value])
  if (error) throw error
  if (!error) navigateTo('/pengunjung')
}

const getKeanggotaan = async () => {
  const { data, error } = await supabase.from('Keanggotaan').select('*')
  if (data) members.value = data
}

const getKeperluan = async () => {
  const { data, error } = await supabase.from('Keperluan').select('*')
  if (data) objectives.value = data
}

onMounted(() => {
  getKeanggotaan()
  getKeperluan()
})
</script>
