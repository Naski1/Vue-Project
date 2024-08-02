<script>
import { reactive } from 'vue';
import { useRouter } from 'vue-router'; // Add this import

export default {
  name: 'ComicList',
  setup() {
    const router = useRouter(); // Initialize the router

    // Simulasi data komik
    const comics = reactive([
      {
        id: 1,
        title: 'Valir with Kyo Kusanagi Skin',
        description: 'Description for Comic 1',
        image: 'https://www.lapakgaming.com/blog/en-my/wp-content/uploads/2024/04/image-20.png'
      },
      {
        id: 2,
        title: 'Masha with Mai Shiranui Skin',
        description: 'Masha with Mai Shiranui Skin',
        image: 'https://www.lapakgaming.com/blog/en-my/wp-content/uploads/2024/04/image-19.png'
      },
      {
        id: 3,
        title: 'Paquito with Terry Bogard Skin',
        description: 'Description for Comic 3',
        image: 'https://www.lapakgaming.com/blog/en-my/wp-content/uploads/2024/04/image-21.png'
      }
    ]);

    // Method untuk navigasi ke halaman detail komik
    const goToDetail = (comic) => {
      router.push({ name: 'comic-detail', params: { id: comic.id.toString() } });
    };

    return {
      comics,
      goToDetail
    };
  }
};
</script>

<template>
  <div class="container mt-5">
    <div class="row row-cols-1 row-cols-md-2 g-4">
      <div class="col" v-for="comic in comics" :key="comic.id">
        <!-- Remove the router-link and use the @click event instead -->
        <div class="card" style="cursor: pointer;" @click="goToDetail(comic)">
          <img :src="comic.image" class="card-img-top" alt="Comic Image" />
          <div class="card-body">
            <h5 class="card-title">{{ comic.title }}</h5>
            <p class="card-text">{{ comic.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>