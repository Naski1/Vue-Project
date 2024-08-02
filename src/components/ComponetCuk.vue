<script scope>
export default {
  data() {
    return {
      comics: [
        {
          image: 'https://cdn.oneesports.id/cdn-data/sites/2/2024/04/Skin-KOF-MLBB-Marsha-1-1024x576.jpg',
          title: 'Comic 1',
          description: 'This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.'
        },
        {
          image: 'https://cdn.oneesports.id/cdn-data/sites/2/2024/04/Skin-KOF-MLBB-Valir-1-1024x576.jpg',
          title: 'Comic 2',
          description: 'This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.'
        }
        // Add more comics as needed
      ]
    };
  },
  methods: {
    goToDetail(comics) {
      this.$router.push({ name: 'comic-detail', params: { id: comics } });
    }
  }
};
</script>

<template>
    <div class="container mt-5">
        <div class="row row-cols-1 row-cols-md-2 g-4">
          <router-link :to="{ name: 'comic-detail', params: { id: comics } }" v-for="(comic, comics) in comics" :key="comics">
            <div class="col">
              <div class="card" style="cursor: pointer;" @click="goToDetail(comics)">
                <img :src="comics.image" class="card-img-top" alt="Comic Image" />
                <div class="card-body">
                  <h5 class="card-title">{{ comics.title }}</h5>
                  <p class="card-text">{{ comics.description }}</p>
                </div>
              </div>
            </div>
          </router-link>
        </div>
      </div>
</template>
