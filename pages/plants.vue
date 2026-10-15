<template>
  <div class="plant-listing">
    <h1>Plant Listing</h1>
    <div class="plants">
      <div
        v-for="plant in plants"
        :key="plant.id"
        class="plant-card"
      >
        <div  class="image-card">
           <img :src="plant.image" :alt="plant.name" />
        </div>        
        
        <h2>{{ plant.name }}</h2>
        <p>{{ plant.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      plants: []
    };
  },
  async mounted() {
    // Fetch the plant data
    const data = await import('~/assets/plants.json');
    this.plants = data.default;
  }
};
</script>

<style scoped>
.plant-listing {
  padding: 20px;
}

.plants {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
}

.plant-card {
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.plant-card img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
}

.plant-card h2 {
  margin: 10px 0;
}

.plant-card p {
  color: #666;
}
.image-card {
 /* width: 200px;  Set a fixed width */
  height: 200px; /* Set a fixed height */
  overflow: hidden; /* Ensure no overflow */
  border-radius: 10px; /* Optional: Add rounded corners */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Optional: Add shadow */
}

.image-card img {
  width: 100%; /* Make the image fill the container's width */
  height: 100%; /* Make the image fill the container's height */
  object-fit: cover; /* Ensures the image covers the area without distortion */
}
</style>