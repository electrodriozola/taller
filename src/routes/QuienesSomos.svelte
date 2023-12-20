<script lang="ts">
  import { fade, fly } from "svelte/transition";
  import { inview } from "svelte-inview";

  let isInView: boolean;
  let scroll: number;

  let parallaxImg1: number;
  let parallaxImg2: number;

  $: parallaxImg1 = scroll / 9;
  $: parallaxImg2 = scroll / 18;
</script>

  <svelte:window bind:scrollY={scroll}></svelte:window>

  <div
  class="wrapper"
  use:inview={{ rootMargin: '-20%' }}
  on:inview_change={({ detail }) => {
    isInView = detail.inView;
  }}
>
  <h2>NUESTRO TALLER</h2>
  {#if isInView}
  <div class="textbox">
    <div in:fly={{delay:250, duration: 800, x: -200}}>
    <h3>Cargado de experiencia</h3>
    <p>
     +20 años reparando motores de todos los tamaños y potencias.
    </p>
  </div>
  <div in:fly={{delay:750, duration: 800, x: -200}}>
    <h3>Vasto equipamiento</h3>
    <p>
     Equipado con las herramientas para solucionar el mas amplio espectro de problemas.
    </p>
  </div>
  <div in:fly={{delay:1250, duration: 800, x: -200}}>
    <h3>Orientados a la Industria</h3>
    <p>
      Acostumbrados a trabajar con motores de gran peso y potencia, reparamos motores de hasta xHP
    </p>
  </div>
  </div>
  <div class="images" in:fly={{ duration: 1000, y:600}} out:fade={{duration: 1000}}>
    <img src="./Foto1.jpg" alt="foto1" class="img1" style:transform={`translateY( ${parallaxImg1}px)`}>
    <img src="./Foto2.jpg" alt="foto1" class="img2" style:transform={`translateY( ${parallaxImg2}px)`}>
  </div>
  {/if}
</div>

<style>
  .wrapper{
    padding: 28px;
    display: grid;
    grid-template-rows: 25% 75%;
    grid-template-areas: "titulo imagenes"
                         "texto imagenes";
    margin-bottom: 60px;
  }
  h2 {
    font-weight:900;
    font-size: 62px;
    letter-spacing: -2px;
    margin: 32px;
    margin-bottom: 0;
    color: black;
    text-align: center;
    text-shadow: -8px 8px 0px #e0e0e0;
  }
  h3{
    margin-bottom: 0;
    margin-top: 20px;
    text-transform: uppercase;
    font-size: 26px;
    font-weight: 700;
  }
  h3::before {
    content: url('./svg/checkbox.svg');
    position: relative;
    top: 8px;
    left: -8px;
  }
  p {
    margin-top: 5px;
    margin-bottom: 0;
    padding-left: 20px;
    color: black;
    font-size: 1.2rem;
  }
  .textbox {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 90%;
    grid-area: texto;
  }
  .textbox div {
    width: 80%;
  }
  .img1{
    width: 50%;
    position: relative;
    height: auto;
    top: -12px;
    left: 20px;
    /* clip-path: polygon(0% 10%, 0% 100%, 100% 90%, 100% 0%);
    -webkit-clip-path: polygon(0% 10%, 0% 100%, 100% 90%, 100% 0%); */
    box-shadow: -8px 8px 0px rgb(10,10,10,.10);
    grid-area: imagenes;
    z-index: 4;
  }
  .img2{
    width: 40%;
    height: auto;
    position: relative;
    /* clip-path: polygon(0% 10%, 0% 100%, 100% 90%, 100% 0%);
    -webkit-clip-path: polygon(0% 10%, 0% 100%, 100% 90%, 100% 0%); */
    box-shadow: -8px 8px 0px rgb(10,10,10,.10);
    grid-area: imagenes;
    z-index: 3;
  }

  @media screen and (max-width: 1100px) {
    .wrapper {
      padding: 0;
      place-items: center;
    }
    .images {
      display: none;
    }
  }
</style>