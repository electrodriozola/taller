<script lang="ts">

  import QuienesSomos from "./QuienesSomos.svelte";
  import NavBar from "./NavBar.svelte";
  import '../styles.css'
  import Servicios from "./Servicios.svelte";
  import Contacto from "./Contacto.svelte";
  import Footer from './Footer.svelte';

</script>

<svelte:head>
  <title>Bobinados y Reparaciones - ODRIOZOLA en Santa Fe</title>
  <meta name="description" content="Somos un taller electromecánico que realiza bobinados y reparaciones de bombas y motores industriales y domésticas. Con mas de 30 años de experienca en el oficio. Ubicados en Colastine Norte, Santa Fe.">
</svelte:head>

<NavBar
></NavBar>
<div class="container background">
  <div class="card">
    <h1>
      <span class="title copper">BOBINADOS</span>
      <span class="title">Y MANTENIMIENTOS</span>
      <span class="title">DE MOTORES Y BOMBAS</span>
    </h1>
    <h2>En Santa Fe Capital</h2>
    <p>Horarios de atención: </p> 
    <p><strong>Lunes a Sábados</strong></p>
    <p><strong>9:30hs a 13:30hs</strong> - <strong>17:30hs a 21:30hs</strong></p>
    <a href="#contacto" class="contactese">Contáctese</a>
  </div>
</div>
<div 
  class="container" id="quienessomos">
  <QuienesSomos></QuienesSomos>
</div>
<div 
class="container" id="servicios">
<Servicios></Servicios>
</div>
<div
  class="container" id="contacto">
  <Contacto></Contacto>
</div>
<Footer/>

 <style>
  .title {
    display: block;
    font-size: 1.4rem;
  }

  .contactese{
    color: #ce6923;
    display: block;
    text-decoration: underline;
    margin-top: 24px;
    font-weight: 600;
    text-align: end;
  }

  strong {
    font-weight: 600;
  }
  h2 {
    margin: 0;
    font-weight: 600;
    text-transform: uppercase;
    border-bottom: 1px solid #333;
    padding-bottom: 12px;
  }
  
  p {
    margin-bottom: 2px;
  }
  p + p{
    margin-top: 2px;
  }

  .copper {
    color: #ce6923;
  }
  .container {
    display: flex;
    width: 100%;
    min-height: 75vh;
  }

  .background {
    height: calc(100vh - 60px);
    background-image: url('$lib/images/bobinado-background.webp');
    background-size: cover;
    background-position: center;
    filter: grayscale(10%);
    -webkit-filter: grayscale(10%);
    padding: 5%;
    padding-top: calc(5% + 108px);
    align-items: center;
    justify-content: baseline;
    box-shadow: inset 0px 4px 16px rgb(10,10,10);
  }

  .card {
    height:auto;
    min-height: 320px;
    max-height: 600px;
    width: 440px;
    background: white;
    padding: 24px;
    border-radius: 12px;
    box-shadow: 0px 4px 16px rgb(10,10,10);
    -webkit-box-shadow: 0px 4px 16px rgb(10,10,10);
    -moz-box-shadow: 0px 4px 16px rgb(10,10,10);
  }

  #quienessomos {
    border-top: 60px solid #303030;
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
    height: 750px;
  }

  #contacto {
    border-top: solid 60px #303030;
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
    #quienessomos{
      height: 650px;
    }
    #servicios {
      height: 1050px;
    }
    #contacto {
      height: 780px;
    }
  }

  @media screen and (max-width: 600px) {
  #quienessomos{
      height:800px;
      padding-top: 48px;
    }
  }

 </style>