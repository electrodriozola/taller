<script lang="ts">
  import { crossfade, fade, fly, scale } from "svelte/transition";
  import { inview } from "svelte-inview";
  // @ts-ignore
  import Carousel from 'svelte-carousel';
  import Lupa from '$lib/lupa.svg?raw';
  import Change from '$lib/change.svg?raw';
  import Fix from '$lib/fix.svg?raw';


  let isInView:boolean;
  let totalWidth: number;
  let isOnMobile: boolean;

  $: isOnMobile = totalWidth < 800 ? true : false; 

  const servicios = [{
    class: "one",
    img: "motores-industriales.webp",
    alt: "",
    h3: "Motores Industriales",
    desc: [
      "Realizamos bobinados y mantenimientos de motores industriales de alta y baja potencia.",
    ]
  },
  {
    class: "two",
    img: "motores-monofasicos.webp",
    alt: "",
    h3: "Motores monofasicos y trifasicos",
    desc: [
      "Bobinamos motores a partir de 1/2hp."
    ]
  },
  {
    class: "three",
    img: "bomba-centrifuga.webp",
    alt: "",
    h3: "Bombas Centrifugas",
    desc: [
      "- Cambio de sellos, rodamientos, turbinas, etc.",
      "- Reparacion/Torneado de ejes, roscas, encamisados, etc."
    ]
  },
  {
    class: "four",
    img: "cortadoras-de-cesped.webp",
    alt: "",
    h3: "Cortadoras de cesped",
    desc: [
      "- Cambio y reparacion de cuchillas, afilado y balanceado.",
      "- Reemplazo de condensadores, llaves, etc."
    ]
  },
  {
    class: "five",
    img: "ventiladores-industriales.webp",
    alt: "",
    h3: "Ventiladores industriales",
    desc: [
      "Realizamos bobinados de ventiladores industriales."
    ]
  },
  ]

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
  <div class="full-container grid">
      {#each servicios as servicio, index}
        <div 
          class="card {servicio.class} servicio"
          style="background-image: url('./{servicio.img}');"
        >
          <div class="bg-black">
            <h3>{servicio.h3}</h3>
            {#each servicio.desc as desc}
              <p>{desc}</p>
            {/each}
          </div>
        </div>
      {/each}
  </div>
</div>

<style>
  .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 28px;
    width: 100%;
  }

  .full-container {
    width: 100%;
    height: 100%;
    max-width: 1020px;
  }
  .grid {
    margin-block: 16px;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
    gap: 8px;
  }
  .card {
    background: gray;
    color: white;
    border-radius: 12px;

    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    box-shadow: inset -15px -60px 82px rgb(10,10,10, .2);
    background-size: cover;
    background-position: center;
    filter: grayscale(80%);
  }

  .card:hover {
    animation-name: scale;
    animation-duration: .3s;
    animation-fill-mode: forwards;
  }
  .card:hover p {
    display: block;
  }
  .card h3 {
    margin-block: 8px;
  }

  .card p {
    margin: 0;
    text-align: start;
    display: none;
  }
  .one {
    grid-column: 1/3;
    grid-row: 1/9;
  }
  .two {
    grid-column: 3/5;
    grid-row: 1/4;
  }
  .three {
    grid-column: 5/9;
    grid-row: 1/7;
  }
  .four {
    grid-column: 3/5;
    grid-row: 4/7;
  }
  .five {
    grid-column: 3/9;
    grid-row: 7/9;
  }
  .bg-black {
    width: 100%;
    background: linear-gradient(transparent, #333);
    padding: 12px;
    border-radius: 0px 0px 8px 8px
  }
  h2 {
    font-weight:900;
    font-size: 52px;
    letter-spacing: -2px;
    margin-block: 26px;

    width: 94%;
    color: black;
    text-align: center;
    text-shadow: -8px 8px 0px rgb(0, 0, 0, .1);
  }
  h3 {
    margin-bottom: 0;
    font-size: 1.3rem;
    font-weight: 600;
    text-transform: capitalize;
  }
  @media screen and (max-width:800px) {
    .wrapper {
      padding: 0;
      justify-content: space-evenly;
    }
    .card {
      margin-inline: 24px;
    }
    .grid {
      grid-template-columns: 1fr;
      grid-template-rows: repeat(5, 160px);
    }
    .one {
      grid-column: 1;
      grid-row: 1;
    }
    .two {
      grid-column: 1;
      grid-row: 2;
    }
    .three {
      grid-column: 1;
      grid-row: 3;
    }
    .four {
      grid-column: 1;
      grid-row: 4;
    }
    .five {
      grid-column: 1;
      grid-row: 5;
    }


    h2 {
      font-size: 3rem;
    }
  }

  @keyframes scale {
    from {
      transform: scale(1);
    }
    to
    {
      transform: scale(1.04);
      border: solid 6px #ce6923;
      border-radius: 10px;
      filter: grayscale(10%);
    }
  }
</style>