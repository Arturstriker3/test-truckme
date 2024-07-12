<script setup lang="ts">

import { ref } from 'vue';

const isMenuOpen = ref(false);

const mobileMenuHandle = () => {
  isMenuOpen.value = !isMenuOpen.value;
  console.log(isMenuOpen.value);
};

</script>

<template>
  <header>
    <div class="container" >
      <nav>
        <div class="logo">
          <img src="./assets/images/logo_truck_me_frete_plataforma.png" alt="truckme-logo">
        </div>
        <ul :class="{'menu-open': isMenuOpen}">
          <div class="btn">
            <i class="close-btn" @click="mobileMenuHandle()" >
              <span class="material-symbols-outlined">
                close
              </span>
            </i>
          </div>
          <li><a href="#">Home</a></li>
          <li><a href="#">Sobre</a></li>
          <li><a href="#">Serviços</a></li>
          <li><a href="#">Contato</a></li>
        </ul>
        <div v-show="!isMenuOpen" class="btn" @click="mobileMenuHandle()">
          <i class="menu-btn">
            <span class="material-symbols-outlined">
              menu
            </span>
          </i>
        </div>
      </nav>
    </div>
  </header>
  <main>
    <section class="home" ref="home" >
      <div class="container">
        <div class="content">
          <div class="text-card">
            <div class="txt">
              <h4>Solução Inteligente em Frete</h4>
              <h2>Essa é a nossa missão!</h2>
            </div>
            <p>
              Lorem ipsum dolor, sit amet consectetur adipisicing elit.
              Praesentium, est repellat.
              Id laboriosam magni ipsum, voluptas error, commodi amet,
              dolore quia modi velit eius reiciendis blanditiis minus illo voluptatem obcaecati?
            </p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<style lang="scss" >

ul {
  list-style: none;
  transition: all 0.5s ease-in-out; /* Transição suave para todas as propriedades */
}

.menu-open {
  left: 0 !important;
  display: flex !important;
  transition: all 0.5s ease-in; /* Transição suave para todas as propriedades */
}

@media (max-width: 768px) {
  ul {
    left: -100%;
    display: none;
    transition: all 0.5s ease-in-out; /* Transição suave para todas as propriedades */
  }

  .menu-open {
    left: 0;
    display: flex;
    transition: all 0.5s ease-in; /* Transição suave para todas as propriedades */
  }
}

@import "./style.scss";

header {
  background-color: $white-color;
  padding: 0.5rem 0;

  .container {
    max-width: 1444px;
    margin: 0 auto;
    width: 100%;
    padding: .5rem 1.5rem;

    @media(max-width: 1024px) {
      padding: 0rem 1rem;
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;

      .logo {
        display: flex;
        justify-content: center;
        align-items: center;
        color: $white-color;

        img {
          width: 300%;
          height: 4rem;
          object-fit: cover;
          margin-right: 8px;
        }
      }

      ul .display {
        left: 0;
        transition: all 0.5s ease-in-out;
      }

      ul {
        display: flex;
        list-style: none;

        @media(max-width: 768px) {
          display: flex;
          flex-direction: column;
          position: absolute;
          width: 100%;
          height: 100vh;
          background: $gray-medium-color;
          top: 80px;
          left: -100%;
          padding: 5rem 0;
          z-index: 9999;
          transition: all 0.5s ease-in;

          &.display {
            left: 0;
            transition: all 0.5s ease-in-out;
          }
        }

        @media(max-width: 728px) {
          display: none;
        }
        
        li {
          margin: 0rem 0.4rem;
          align-items: center;
          padding: 0.5rem 0.5rem;

          @media(max-width: 840px) {
            margin: 0 0.2rem;
          }

          a {
            text-decoration: none;
            font-size: 1.1rem;
            letter-spacing: 2.5px;
            padding: 0.7rem 1rem;
            color: $black-color;

            &:hover {
              color: $gray-dark-color;
              filter: brightness(0.9);
            }

            @media(max-width: 768px) {
              display: block;
              margin: 10px;
            }

            @media(max-width: 840px) {
              letter-spacing: 2.5px;
              color: $black-color;
              padding: 0.7rem 1rem;
            }
            
          }
        }
      }

      .btn {
        font-size: 1.3rem;
        color: $black-color;
        cursor: pointer;
        display: none;

        @media(max-width: 768px) {
          display: block;
        }

        i {
          .material-symbols-outlined{
            font-size: 2.5rem;
          }
        }

        &:hover {
          color: $gray-dark-color;
          filter: brightness(0.9);
        }
      }
    }
  }
}

main {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  background-color: $white-color;

  .home {

    .container {
      max-width: 1444px;
      margin: 0 auto;
      width: 100%;
      padding: 1.5rem 1.5rem;
      border-radius: 8px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
      height: 600px;
      
      background-image: url("./assets/images/banner_truck_me.jpeg");
      background-size: cover;
      background-position: center;
      filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

      display: flex;
      justify-content: flex-end;
      align-items: flex-end;

      .content {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        width: 50%;
        
        padding: 4px;
        border-radius: 10px;
        background-color: $gray-light-color;
        filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

        @media(max-width: 840px) {
          text-align: center;
        }

        .text-card {

          .txt {
            h4 {
              text-align: center;
              font-size: 2rem;
            }

            h2 {
              font-size: 4.1rem;

              @media(max-width: 728px) {
                font-size: 2rem;
              }
            }
          }

          p {
            font-size: 1rem;
            line-height: 1.4;
            margin: 1rem 0.5rem;
            text-align: justify;

            @media(max-width: 840px) {
                width: 100%;
            }

            @media(max-width: 728px) {
              font-size: 0.9rem;
            }
          }
        }
      }
    }
  }
}

.button {
  background-color: $primary-color;
  color: $black-color;

  &:hover {
      background-color: $gray-dark-color;
  }
}

</style>
