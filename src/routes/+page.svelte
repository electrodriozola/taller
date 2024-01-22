<script lang="ts">

  import QuienesSomos from "./QuienesSomos.svelte";
  import NavBar from "./NavBar.svelte";
  import '../styles.css'
  import Servicios from "./Servicios.svelte";
  import Contacto from "./Contacto.svelte";
  import Footer from './Footer.svelte';

</script>

<svelte:head>
  <title>ODRIOZOLA Electromecanica</title>
  <meta name="description" content="Ubicados en Santa Fe, Santa Fe; somos un taller electromecanico que repara bombas industriales y domesticas. Con mas de 20 años de experienca en el oficio.">
</svelte:head>

<NavBar
></NavBar>
<div class="container background">
  <div class="card">
    <h1>Traenos tu motor, nosotros hacemos el resto</h1>
  </div>
</div>
<div 
class="container" id="servicios">
<Servicios></Servicios>
</div>
<div 
  class="container" id="quienessomos">
  <QuienesSomos></QuienesSomos>
</div>
<div
  class="container" id="contacto">
  <Contacto></Contacto>
</div>
<Footer/>

 <style>

  .container {
    display: flex;
    width: 100%;
    min-height: 85vh;
  }

  .background {
    height: calc(100vh - 60px);
    background-image: url('$lib/images/bobinado-background.jpg');
    background-size: cover;
    filter: grayscale(20%);
    -webkit-filter: grayscale(20%);
    padding: 5%;
    padding-top: calc(5% + 108px);
    align-items: center;
    justify-content: baseline;
    box-shadow: inset 0px 4px 16px rgb(10,10,10);
  }

  .card {
    height: 100%;
    min-height: 320px;
    max-height: 500px;
    width: 440px;
    background: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0px 4px 16px rgb(10,10,10);
    -webkit-box-shadow: 0px 4px 16px rgb(10,10,10);
    -moz-box-shadow: 0px 4px 16px rgb(10,10,10);
  }

  #quienessomos {
    border-top: 60px solid #1c542d;
    background: white;
    width: 100%;
    height: 600px;
    z-index: 1;
  }

  #servicios {
    border-top: 60px solid #303030;
    position: relative;
    background: white;
    z-index: 6;
    height: 700px;
  }

  #contacto {
    border-top: solid 60px #073980;
  }

  @media screen and (max-width: 800px) {
    .container{
      height: auto;
      min-height: 75vh;
    }
    .card {
      align-self: center;
    } 
    .background {
      justify-content: center;
      padding-top: calc(5% + 70px);
    } 
    #servicios {
      height: 660px;
    }
    #contacto {
      height: 780px;
    }
  }

  @media screen and (max-width: 600px) {
  #quienessomos{
      height: 880px;
    }
  }

 </style>