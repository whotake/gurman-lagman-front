<template>
  <div id="app">
    <div class="container">
      <div class="header">
        <b-nav justified="True">
          <b-nav-item active>Главная</b-nav-item>
          <b-nav-item>Статьи</b-nav-item>
          <b-nav-item>Места</b-nav-item>
        </b-nav>
      </div>
      <div class="content">
        <router-view/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
};
</script>
