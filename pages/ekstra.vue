<template>
  <div class="profile-page">
<!-- Judul Halaman -->
<div class="page-title">
  <h1 class="judul">Ekstrakulikuler</h1> 
  <p>SMK Negeri 4 Tasikmalaya</p>
</div>
  <div class="image-gallery">
    <div v-for="(eskul,i) in eskul" :key="i" class="container">
      <img :src="eskul.foto" alt="eskul" class="image">
      <div class="overlay">{{ eskul.nama }}</div>
    </div>
  </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()
const eskul = ref([])

const getEskul = async () => {
  const { data, error } = await supabase.from('eskul').select(`*`)    
  if (data) eskul.value = data;
}
onMounted(() => {
  getEskul()
})
</script>

<style scoped>
* {
box-sizing: border-box;
margin: 0;
padding: 0;
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
color: #333;;
font-weight: bold;
}

.page-title p {
font-size: 2.5rem;
color: #333;
font-weight: bold;
}

body {
font-family: Arial, sans-serif;
}

.image-gallery {
display: flex;
flex-wrap: wrap; /* Agar gambar bisa masuk ke baris berikutnya */
justify-content: space-around; /* Memberi jarak antar gambar */
gap: 1rem; /* Jarak antar gambar */
margin-top: 3rem;
padding: 10px;
}

.container {
position: relative;
width: 100%;
max-width: 300px;
 /* Lebar maksimum gambar */
}

.image {
display: block;
width: 100%;
height: auto;
}

.overlay {
position: absolute;
bottom: 0;
background: rgba(0, 0, 0, 0.5); /* Black see-through */
color: #f1f1f1;
width: 100%;
transition: 0.5s ease;
opacity: 0;
font-size: 20px;
padding: 10px;
text-align: center;
}

.container:hover .overlay {
opacity: 1;
}

</style>