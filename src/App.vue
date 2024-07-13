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
            <i class="close-btn">
              <span @click="mobileMenuHandle()" class="material-symbols-outlined">
                close
              </span>
            </i>
          </div>
          <div class="hover-brightness" style="display: flex; flex-direction: row; justify-content: center; align-items: center; margin-left: -1rem;" >
            <i v-if="isMenuOpen" class="close-btn">
              <span class="material-symbols-outlined">
                home
              </span>
            </i>
            <li><a href="#">Home</a></li>
          </div>
          <div class="hover-brightness" style="display: flex; flex-direction: row; justify-content: center; align-items: center; margin-left: -1rem;" >
            <i v-if="isMenuOpen" class="close-btn" >
              <span class="material-symbols-outlined">
                info
              </span>
            </i>
            <li><a href="#">Sobre</a></li>
          </div>
          <div class="hover-brightness" style="display: flex; flex-direction: row; justify-content: center; align-items: center; margin-left: 1rem;" >
            <i v-if="isMenuOpen" class="close-btn">
              <span class="material-symbols-outlined">
                work
              </span>
            </i>
            <li><a href="#">Serviços</a></li>
          </div>
          <div class="hover-brightness" style="display: flex; flex-direction: row; justify-content: center; align-items: center; margin-left: 1rem;" >
            <i v-if="isMenuOpen" class="close-btn">
              <span class="material-symbols-outlined">
                call
              </span>
            </i>
            <li><a href="#">Contato</a></li>
          </div>
        </ul>
        <div v-show="!isMenuOpen" class="btn">
          <i class="menu-btn">
            <span @click="mobileMenuHandle()" class="material-symbols-outlined">
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
              Na vanguarda da revolução logística,
              a TruckMe se destaca como a primeira transportadora 100% digital do mercado.
              Nosso compromisso é oferecer uma solução inteligente em fretes,
              combinando tecnologia de ponta com um serviço personalizado e eficiente.
            </p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<style lang="scss" >

@import "./style.scss";

ul {
  list-style: none;
  transition: all 0.5s ease-in-out !important;
}

.hover-brightness:hover {
  @media(max-width: 768px) {
    background-color: $primary-color;
  }
}

.menu-open {
  margin-top: -3.8rem!important;
  top: 0 !important ;
  left: 0 !important;
  display: flex !important;
  transition: all 0.5s ease-in !important;
  height: 100%;
  
  li {
    display: flex;
    justify-content: center;
    align-content: center;
  }
  
  .btn {
    i {
      .material-symbols-outlined {
        margin-right: 1.2rem;
      }
    }
  }
}

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

          @media(max-width: 825px) {
            height: 3rem;
          }

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
          top: 0;
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
        text-align: right;

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
  padding: 1.5rem;

  .home {
    width: 100%;

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

      @media(max-width: 425px) {
        height: 400px;
      }

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
          width: 100%;
        }

        .text-card {

          .txt {
            h4 {
              text-align: center;
              font-size: 2rem;

              @media(max-width: 1100px) {
                font-size: 1.5rem;
              }

              @media(max-width: 900px) {
                font-size: 1.5rem;
              }

              @media(max-width: 800px) {
                font-size: 1.3rem;
              }

              @media(max-width: 730px) {
                font-size: 1rem;
              }

              @media(max-width: 425px) {
                font-size: .7rem;
              }

              @media(max-width: 320px) {
                font-size: .7rem;
              }

            }

            h2 {
              font-size: 4rem;
              color: $primary-color;
              text-align: center;

              @media(max-width: 1450px) {
                font-size: 3.5rem;
              }

              @media(max-width: 1300px) {
                font-size: 3rem;
              }

              @media(max-width: 1115px) {
                font-size: 2.5rem;
              }

              @media(max-width: 1064px) {
                font-size: 2.5rem;
              }

              @media(max-width: 950px) {
                font-size: 2rem;
              }

              @media(max-width: 730px) {
                font-size: 1.5rem;
              }

              @media(max-width: 425px) {
                font-size: 1rem;
              }
            }
          }

          p {
            font-size: 1rem;
            line-height: 1.4;
            padding: 1rem 0.5rem;
            text-align: justify;

            @media(max-width: 425px) {
              font-size: 0.9rem;
            }

            @media(max-width: 728px) {
              font-size: 0.9rem;
            }

            @media(max-width: 768px) {
              display: none;
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
