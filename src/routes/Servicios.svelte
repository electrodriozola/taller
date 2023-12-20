<script lang="ts">
  import { crossfade, fade, fly, scale } from "svelte/transition";
  import { inview } from "svelte-inview";
  // @ts-ignore
  import Carousel from 'svelte-carousel';
  import Lupa from '$lib/lupa.svg?raw';
  import Change from '$lib/change.svg?raw';
  import Fix from '$lib/fix.svg?raw';


  let isInView:boolean;
  let carousel;
  let totalWidth: number;
  let isOnMobile: boolean;

  $: isOnMobile = totalWidth < 800 ? true : false; 

  const servicios = [{
    svg: Lupa,
    h3: "DIAGNOSTICO",
    p: "Analizamos a fondo las fallas visuales, sonoras y de trabajo de los motores",
    num: 1
  },
  {
    svg: Change,
    h3: "REEMPLAZO DE PARTES",
    p: "Reemplazamos las piezas dañadas o rotas con las mejores opciones disponibles en el mercado",
    num: 2
  },
  {
    svg: Fix,
    h3: "REPARACION ARTESANAL",
    p: "Correjimos artesanalmente al milimetro aquellas partes imposibles de cambiar",
    num: 3
  }]

</script>
  <svelte:window 
    bind:outerWidth={totalWidth}
    ></svelte:window>

  <div
  class="wrapper"
  use:inview={{ rootMargin: '-30%' }}
  on:inview_change={({ detail }) => {
    isInView = detail.inView;
  }}
  >
  <h2>SERVICIOS</h2>
  {#if isInView}
  <div class="array-servicios" in:fade>
  <Carousel 
    bind:this={carousel}
    arrows={false}
    autoplay={isOnMobile}
    dots={isOnMobile}
    swiping={isOnMobile}
    particlesToShow={isOnMobile ? 1 : 3 }
  >
    {#each servicios as servicio, index}
      <div class="servicio">
        <div class="svg">
          {@html servicio.svg}
          <div class="numero"><p>{index+1}</p></div>
        </div>
        <h3>{servicio.h3}</h3>
        <p>{servicio.p}</p>
      </div>
    {/each}
  </Carousel>
  </div>
  {/if}
</div>

<style>
  .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 28px;
    width: 100%;
  }
  .servicio {
    width: 100%;
  }
  .servicio .svg{
    width: 230px;
    height: 230px;
    max-width: 300px;
    aspect-ratio: 1 / 1;
    justify-content: center;
    background: white;
    border-radius: 50%;
    border: solid 6px black;
    box-shadow: 0px 0px 50px -28px rgba(0,0,0,0.62);
-webkit-box-shadow: 0px 0px 50px -28px rgba(0,0,0,0.62);
-moz-box-shadow: 0px 0px 50px -28px rgba(0,0,0,0.62);
  }
  .servicio .numero {
    position:fixed;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    top: 20px;
    margin-right: 150px ;
    z-index: 3;
    padding: 8px;
    background: #202020;
  }
  .servicio .numero p {
    padding: 0;
    margin: 0;
    color: white;
    font-weight: 700;
  }
  h2 {
    font-weight:900;
    font-size: 62px;
    letter-spacing: -2px;
    margin: 32px;
    margin-bottom: 0;
    width: 94%;
    color: black;
    text-align: center;
    text-shadow: -8px 8px 0px #e0e0e0;
  }
  h3 {
    margin-bottom: 0;
    font-size: 1.2rem;
  }
  .array-servicios {
    margin-block: 35px;
    display: flex;
    width: 80%;
    justify-content: center;
    align-items: center;
    gap: 20px;
  }
  .array-servicios div {
    display: flex;
    width: max-content;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding-block: 20px;
    max-width: 320px;
  }
  .array-servicios div p {
    max-width: 300px;
    font-weight: 300;
    font-size: 18px;
    margin-top: 6px;
  }

  @media screen and (max-width:800px) {
    .wrapper {
      padding: 0;
      justify-content: space-evenly;
    }
    h2 {
      font-size: 3rem;
    }
  }
</style>