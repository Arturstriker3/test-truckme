<script setup lang="ts">

import { ref, watch } from 'vue';

const isMenuOpen = ref(false);
const isReadMoreOpen = ref(false);

const mobileMenuHandle = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const ReadMoreHandle = () => {
  isReadMoreOpen.value = !isMenuOpen.value;
};

watch(isMenuOpen, (newVal) => {
  if (newVal) {
    document.body.classList.add('no-scroll');
  } else {
    document.body.classList.remove('no-scroll');
  }
});

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

    <section class="about" ref="about" >
      <div class="container">
        <div class="content" >
          <div class="content-header" >
            <h3>Sobre</h3>
          </div>
          <div class="content-body" >
            <button v-if="!isReadMoreOpen" @click="ReadMoreHandle()">
              <p>
                Leia mais
              </p>
            </button>
            <div class="about-text" v-else>
              <div class="message-header" >
                <div style="display: flex; justify-content: center; align-items: center; flex-direction: row; gap: .4rem;" >
                  <h3>Embarcadores,</h3>
                  <p>nós fazemos frete!</p>
                </div>
                <span>Através da nossa Plataforma Web, garantimos serviço com todos os requisitos e obrigações da transportadora tradicional.</span>
              </div>
              <div class="message-text" >
                Conectamos vocês Embarcadores aos mais qualificados transportadores autônomos,
                através de um criterioso processo de gestão e simplificação de processos do frete!
                Com a TruckMe, você otimiza seus custos de transporte.
                Nossa solução digital permite a melhor combinação de rotas e cargas,
                resultando em menor tempo de entrega e redução de despesas operacionais.
                Descubra como a TruckMe pode transformar a logística do seu negócio.
                Junte-se à primeira transportadora 100% digital e leve suas operações de frete para o próximo nível.
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="services" ref="services" >
      <div class="container">
        <div class="content" >
          <div class="content-header" >
            <h3>Serviços</h3>
          </div>
          <div class="content-body">
            <div class="grid-item">
              titulo
            </div>
            <div class="grid-item">Item 2</div>
            <div class="grid-item">Item 3</div>
            <div class="grid-item">Item 4</div>
            <div class="grid-item">Item 5</div>
            <div class="grid-item">Item 6</div>
            <div class="grid-item">Item 7</div>
            <div class="grid-item">Item 8</div>
          </div>
        </div>
      </div>
    </section>

    <section class="contact" ref="contact" >
      <div class="container">
        <div class="content" >
          <div class="content-header" >
            <h3>Contato</h3>
          </div>
          <div class="content-body" >
            
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<style lang="scss" >

@import "./style.scss";

.no-scroll {
  overflow: hidden;
}

ul {
  list-style: none;
  transition: all 0.5s ease-in-out !important;
}

.hover-brightness {
  min-width: 150px;
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

          @media(max-width: 920px) {
            height: 3rem;
          }

          @media(max-width: 801px) {
            height: 2.5rem;
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
          height: 100%;
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
              filter: brightness(0.9) blur(.5px);
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
  flex-direction: column;
  gap: 4rem;
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

          padding:.2rem;

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

  .about {
    width: 100%;

    .container {
      margin: 0 auto;
      width: 100%;
      border-radius: 8px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
      height: 600px;
      
      filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

      .content {

        display: flex;
        flex-direction: column;
        height: 100%;
        width: 100%;
        
        border-radius: 10px;
        background-color: $gray-light-color;
        filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

        .content-header {

          width: 100%;
          display: flex;
          justify-content: flex-start;
          align-items: center;
          background: $gray-medium-color;
          border-top-left-radius: 10px;
          border-top-right-radius: 10px;
          padding: 8px;
          filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

          h3 {
            font-size: 2rem;
            color: $black-color;
            text-align: center;
          }
        }

        .content-body {
          padding: 4px;
          display: flex;
          justify-content: center;
          align-items: center;
          width: 100%;
          height: 100%;

          .about-text {
            height: 100%;
            width: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            padding: 4rem;

            @media(max-width: 425px) {
              padding: 0 1rem;
            }

            .message-header {

              display: flex;
              justify-content: left;
              align-items: flex-start;
              flex-direction: column;
              width: 100%;

              h3 {
                font-size: 2.5rem;

                @media(max-width: 768px) {
                  font-size: 2rem;
                }

                @media(max-width: 685px) {
                  font-size: 2rem;
                }

                @media(max-width: 425px) {
                  font-size: 1.1rem;
                }

                @media(max-width: 320px) {
                  font-size: 0.7rem;
                }

                
              }

              p {
                color: $primary-color;
                font-weight: 600;
                font-size: 2.5rem;

                @media(max-width: 768px) {
                  font-size: 2.2rem;
                }

                @media(max-width: 685px) {
                  font-size: 1.9rem;
                }

                @media(max-width: 634px) {
                  font-size: 1.6rem;
                }

                @media(max-width: 621px) {
                  font-size: 1.5rem;
                }

                @media(max-width: 425px) {
                  font-size: 1.2rem;
                }

                @media(max-width: 372px) {
                  font-size: 0.82rem;
                }
              }

              span {
                color: $gray-dark-color;
                font-weight: bolder;
                font-size: 1.2rem;

                @media(max-width: 425px) {
                  font-size: 1rem;
                }
                @media(max-width: 372px) {
                  font-size: 0.9rem;
                }
              }
            }

            .message-text {
              display: flex;
              justify-content: center;
              align-items: center;
              font-weight: 500;
              font-size: 1.2rem;
              padding: .8rem 0;
              width: 100%;

              // background-color: $gray-medium-color;
              // border-radius: 8px;

              @media(max-width: 768px) {
                display: none;
              }
            }
          }
        }
      }
    }
  }

  .services {
    width: 100%;

    .container {
      // max-width: 1444px;
      margin: 0 auto;
      width: 100%;
      border-radius: 8px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
      height: 600px;
      
      filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

      .content {
        display: flex;
        flex-direction: column;
        height: 100%;
        width: 100%;
        
        border-radius: 10px;
        background-color: $gray-light-color;
        filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

        .content-header {

          width: 100%;
          // height: 2rem;
          display: flex;
          justify-content: flex-start;
          align-items: center;
          background: $gray-medium-color;
          border-top-left-radius: 10px;
          border-top-right-radius: 10px;
          padding: 8px;
          filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

          h3 {
            font-size: 2rem;
            color: $black-color;
            text-align: center;
          }
        }

        .content-body {
          padding: 4px;
          display: grid;
          grid-template-columns: repeat(4, 1fr);
          grid-template-rows: repeat(2, auto);
          gap: 10px;
          height: 100%;

          .grid-item {
            background-color: #f0f0f0;
            padding: 20px;
            text-align: center;
            border: 1px solid #ddd;
          }
        }
      }
    }
  }

  .contact {
    width: 100%;

    .container {
      // max-width: 1444px;
      margin: 0 auto;
      width: 100%;
      border-radius: 8px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
      height: 600px;
      
      filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

      .content {
        display: flex;
        flex-direction: column;
        height: 100%;
        width: 100%;
        
        border-radius: 10px;
        background-color: $gray-light-color;
        filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

        .content-header {

          width: 100%;
          // height: 2rem;
          display: flex;
          justify-content: flex-start;
          align-items: center;
          background: $gray-medium-color;
          border-top-left-radius: 10px;
          border-top-right-radius: 10px;
          padding: 8px;
          filter: drop-shadow(0 0 0.75rem rgba(0, 0, 0, 0.3));

          h3 {
            font-size: 2rem;
            color: $black-color;
            text-align: center;
          }
        }

        .content-body {
          padding: 4px;
        }
      }
    }
  }
}

button {
  background-color: $primary-color;
  color: $white-color;
  border-radius: 50px 50px 50px 50px;
  font-size: 18px;
  padding: 20px 40px;
  cursor: pointer;
  border: 4px solid $gray-medium-color;

  &:hover {
    background-color: $gray-dark-color;
    p {
      filter: blur(.5px);
    }
  }
}

</style>
