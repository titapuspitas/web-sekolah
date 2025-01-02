<template>
  <div class="profile-page">
    <!-- Judul Halaman -->
    <div class="page-title">
      <h1 class="judul">Galeri</h1>
      <p>SMK Negeri 4 Tasikmalaya</p>
    </div>
    <h1 class="gallery-title">
    MPLS 2024
    <div class="title-underline"></div>
</h1>
<div class="image-gallery">
      <div v-for="(mpls,i) in mpls" :key="i" class="container">
      <img :src="mpls.foto" alt="mpls" class="image">
      </div>
    </div>
  </div>
  <h1 class="gallery-title">
      Perkemahan P5 2024
      <div class="title-underline"></div>
  </h1>
    <div class="image-gallery">
      <div v-for="(pramuka ,i) in pramuka " :key="i" class="container">
      <img :src="pramuka .foto" alt="pramuka " class="image">
      </div>
  </div>
  <h1 class="gallery-title">
      Upacara Memperingari 17 Agustus 
      <div class="title-underline"></div>
  </h1>
    <div class="image-gallery">
      <div v-for="(galeri ,i) in galeri " :key="i" class="container">
      <img :src="galeri .foto" alt="galeri " class="image">
      </div>
  </div>
  <h1 class="gallery-title">
      Job Fair 2024 
      <div class="title-underline"></div>
  </h1>
    <div class="image-gallery">
      <div v-for="(jobfair ,i) in jobfair " :key="i" class="container">
      <img :src="jobfair .foto" alt="jobfair " class="image">
      </div>
  </div>

</template>

<script setup>
const supabase = useSupabaseClient()
const mpls = ref([])
const pramuka = ref([])
const galeri = ref([])
const jobfair = ref([])

const getMpls = async () => {
  const { data, error } = await supabase.from('mpls').select(`*`)    
  if (data) mpls.value = data;
}
const getPramuka = async () => {
  const { data, error } = await supabase.from('pramuka ').select(`*`)    
  if (data) pramuka .value = data;
}
const getGaleri = async () => {
  const { data, error } = await supabase.from('galeri').select(`*`)    
  if (data) galeri .value = data;
}
const getJobFair = async () => {
  const { data, error } = await supabase.from('jobfair').select(`*`)    
  if (data) jobfair .value = data;
}
onMounted(() => {
  getMpls()
  getPramuka()
  getGaleri()
  getJobFair()
})
</script>
<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.gallery-title {
  font-size: 25px;
  color: #333;
  margin-top: 50px;
  font-weight: bold;
  text-align: center;
  margin-bottom: 32px;
  position: relative;
}

.title-underline {
  width: 100%;
  height: 2px;
  background-color: #333;
  margin: 20px auto 0;
}

.profile-page {
  margin-top: 100px;
}

.judul {
  font-size: 2.5rem;
  color: #333;
}

.page-title {
  text-align: center;
  margin-bottom: 1rem;
  padding-top: 30px;
}

.page-title h1 {
  font-size: 2.5rem;
  color: #333;
  font-weight: bold;
}

.page-title p {
  font-size: 1.2rem;
  color: #333;
  font-weight: bold;
}

.image-gallery {
  display: flex;
  flex-wrap: wrap; 
  justify-content: space-around; 
  gap: 5px; 
  margin-top: 1rem;
  padding: 25px;
  object-fit: contain;
}

.container {
  position: relative;
  width: 100%;
  max-width: 300px;
  height: 400px; 
  overflow: hidden; 
}

.image {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover; 
}


</style>
