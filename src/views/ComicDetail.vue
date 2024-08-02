<template>
    <div class="container mt-5">
      <div class="card">
        <img :src="comic.image" class="card-img-top" alt="Comic Image" />
        <div class="card-body">
          <h5 class="card-title">{{ comic.title }}</h5>
          <p class="card-text">{{ comic.description }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { computed } from 'vue';
  import { useRoute } from 'vue-router';
  
  export default {
    name: 'ComicDetail',
    setup() {
      const route = useRoute();
  
      // Ambil id dari parameter route
      const comicId = computed(() => route.params.id);
  
      // Simulasi data detail komik berdasarkan id
      const comics = [
        {
          id: '1',
          title: 'Valir with Kyo Kusanagi Skin',
          description: 'Description for Comic 1',
          image: 'https://www.lapakgaming.com/blog/en-my/wp-content/uploads/2024/04/image-20.png'
        },
        {
          id: '2',
          title: 'Masha with Mai Shiranui Skin',
          description: 'Masha with Mai Shiranui Skin',
          image: 'https://www.lapakgaming.com/blog/en-my/wp-content/uploads/2024/04/image-19.png'
        },
        {
          id: '3',
          title: 'Paquito with Terry Bogard Skin',
          description: 'Description for Comic 3',
          image: 'https://www.lapakgaming.com/blog/en-my/wp-content/uploads/2024/04/image-21.png'
        }
      ];
  
      // Ambil data komik berdasarkan comicId
      const comic = comics.find(c => c.id === comicId.value);
  
      return {
        comic
      };
    }
  };
  </script>
  
  <style>
  /* Tambahkan style card sesuai kebutuhan */
  </style>
  