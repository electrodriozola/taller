<script lang="ts">
  import { fade, fly } from 'svelte/transition';
  import { inview } from 'svelte-inview';

  import WhatsAppImage from "$lib/images/whatsapp.png"
  import EmailImage from "$lib/images/email.png"
  import GooglePinImage from "$lib/images/googlePin.png"

  let isInView: boolean;


</script>

<section>
  <h2>CONTACTO</h2>
  <div
  class="wrapper"
  use:inview={{ rootMargin: '-10%' }}
  on:inview_change={({ detail }) => {
    isInView = detail.inView;
  }}
>
  {#if isInView}
  <div class="box-array">
    <a href="https://wa.link/my4ams" target="_blank" in:fly={{duration:500, delay:500, y:100}} class="box">
      <img src={WhatsAppImage} alt="Logo de whatsapp">
      <div>
        <h3>WHATSAPP</h3>
        <p>+54 342 508 2986</p>
      </div>
    </a>
    <a href="mailto:electrodriozola@gmail.com" target="_blank" in:fly={{duration:500, delay:1000, y:100}} class="box">
      <img src={EmailImage} alt="Sobre de correo">
      <div>
      <h3>CORREO</h3>
      <p>electrodriozola@gmail.com</p>
      </div>
    </a>
    <a href="https://maps.app.goo.gl/rNEAAPGpZj1zi8iv8" target="_blank" in:fly={{duration:500, delay:1500, y:100}} class="box">
      <img src={GooglePinImage} alt="Pin de Ubicacion">
      <div>
      <h3>COMO LLEGAR</h3>
      <!-- <p>Los Jazmines 6005</p> -->
      <!-- <p>Colastine Norte</p> -->
      </div>
    </a>
  </div>
  {/if}
</div>
</section>

<style>
  p {
    padding: 0;
    margin: 0;
  }
  h3 {
    margin-bottom: 4px;
  }
  section{
    display: flex;
    flex-direction: column;
    padding: 28px;
    width: 100%;
  }
  .box-array {
    display: flex;
    height: 100%;
    justify-content: center;
    gap: 12px;
  }
  h2 {
    font-weight:900;
    font-size: 62px;
    letter-spacing: -2px;
    margin: 20px;
    margin-bottom: 12px;
    color: black;
    text-shadow: -8px 8px 0px #e0e0e0;
  }
  h3 {
    margin-block: 6px;
    font-size: 1.2rem;
  }
  .wrapper {
    margin-top: 30px;
    width: 100%;
  }

  img {
    width: 100px;
  }

  .box {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 300px;
    height: 300px;
    background: white;
    border: 7px solid #d9d9d9;
    padding: 25px;
    border-radius: 10px;
    text-decoration: none;
    color: black;
  }
  
  .box div{
      display: flex;
      width: 70%;
      flex-direction: column;
      justify-content: center;
      text-align: center;
      align-items: center;
    }

  .box:hover {
    border: 7px solid #ce6923;
  }
  .box:hover img{
    animation: rotate-scale 1s alternate ease-in-out;
  }

  @keyframes rotate-scale {
    0%   {transform: scale(1)  rotate(0deg);}
    25%  {transform: scale(1.5) rotate(120deg);}
    50%  {transform: scale(.75) rotate(240deg);}
    100% {transform: scale(1) rotate(360deg);}
  }

  @media screen and (max-width: 800px) {
    h2 {
      margin: 26px 0 0 0;
      text-align: center;
      font-size: 2.8rem;
    }
    a p {
      font-size: .8rem;
    }
    section {
      padding: 0;
    }
    .box-array {
      flex-direction: column;
      align-items: center;
      gap: 12px;
    }
    .box {
      flex-direction: row;
      height: 180px;
      width: 310px;
      justify-content: space-between;

    } 
    .box div{
      display: flex;
      width: 70%;
      flex-direction: column;
      justify-content: center;
      text-align: center;
      align-items: center;
    }
    .box img {
      width: 64px;
    }
  }
</style>