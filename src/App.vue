<script setup lang="ts">



</script>

<template>
  
  <header>
    <div class="container" >
      <nav>
        <div class="logo">
          <img src="./assets/images/logo_truck_me_frete_plataforma.png" alt="truckme-logo">
          <h2><span>truck</span>me</h2>
        </div>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">Sobre</a></li>
          <li><a href="#">Serviços</a></li>
          <li><a href="#">Contato</a></li>
        </ul>
      </nav>
    </div>
  </header>

</template>

<style lang="scss" >

@import "./style.scss";

header {
    background-color: $white-color;
}

.button {
    background-color: $primary-color;
    color: $black-color;

    &:hover {
        background-color: $gray-dark-color;
    }
}

</style>
