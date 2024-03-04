<script lang="ts">
  import { fade, fly } from "svelte/transition";
  import { inview } from "svelte-inview";
  //@ts-ignore
  import Carousel from 'svelte-carousel'

  let isInView: boolean;
  let scroll: number;
</script>

  <svelte:window bind:scrollY={scroll}></svelte:window>

  <div
  class="wrapper"
  use:inview={{ rootMargin: '-20%' }}
  on:inview_change={({ detail }) => {
    isInView = detail.inView;
  }}
>
  <h2>EL TALLER</h2>
  {#if isInView}
  <div class="textbox">
    <div in:fly={{delay:250, duration: 800, x: -200}}>
    <h3>Cargado de experiencia</h3>
    <p>
     +30 años reparando motores de todos los tamaños y potencias.
    </p>
  </div>
  <div in:fly={{delay:750, duration: 800, x: -200}}>
    <h3>Vasto equipamiento</h3>
    <p>
     Equipado con las herramientas necesarias para solucionar el mas amplio espectro de problemas.
    </p>
  </div>
  <div in:fly={{delay:1250, duration: 800, x: -200}}>
    <h3>Orientados a la Industria</h3>
    <p>
      Habituados a trabajar con motores de gran peso y potencia, habiendo reparado motores de hasta 150HP.
    </p>
  </div>
  </div>
  <!-- <div class="images" in:fly={{ duration: 1000, x :600}} out:fade={{duration: 1000}}>
    <img src="./Foto1.jpg" alt="foto1" class="img1">

  </div> -->
  {/if}
</div>

<style>
  .wrapper{
    padding: 28px;
    width: 100%;
    display: grid;
    grid-template-areas: "titulo"
                         "texto";
    margin-bottom: 60px;
  }
  h2 {
    font-weight:900;
    font-size: 4rem;
    letter-spacing: -2px;
    margin: 32px;
    margin-bottom: 0;
    color: black;
    text-shadow: -8px 8px 0px #e0e0e0;
    margin-inline: auto;
  }
  h3{
    margin-bottom: 0;
    margin-top: 20px;
    text-transform: uppercase;
    font-size: 26px;
    font-weight: 700;
    text-align: center;
  }
  h3::before {
    content: url('$lib/checkbox.svg');
    position: relative;
    top: 8px;
    left: -8px;
  }
  p {
    margin-top: 5px;
    margin-bottom: 0;
    padding-left: 20px;
    text-align: center;
    color: black;
    font-size: 1.2rem;
  }
  .textbox {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
    grid-area: texto;
  }
  .textbox div {
    width: 60%;
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

  @media screen and (max-width: 600px) {
    h2 {
      margin: 0;
      font-size: 3rem;
    }
    .textbox div{
      width: 75%;
    }
  }
</style>