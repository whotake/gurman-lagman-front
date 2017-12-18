<template>
  <div>
    <div v-if="isLoading">
      <h1 class="text-center">Загрузак</h1>
    </div>
    <div v-if="places">
      <div v-for="item in places" class="card" style="width: 20rem;">
        <div class="card-body">
          <h4 class="card-title">{{ item.name }}</h4>
          <p class="card-text">{{ item.description }}</p>
          <a href="#" class="btn btn-primary">Подробнее</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import http from '../api/network';

  export default {
    name: 'index-page',
    data() {
      return {
        isLoading: false,
        places: undefined,
      };
    },
    created() {
      this.fetchData();
    },
    methods: {
      fetchData() {
        this.isLoading = true;

        http.get('place/').then((response) => {
          this.places = response.data;
          this.isLoading = false;
        });
      },
    },
  };
</script>
