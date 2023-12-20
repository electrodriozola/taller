<script lang="ts">
    import { fly } from 'svelte/transition';
  import '../styles.css'
 
  let scroll: number;
  let totalHeight: number;
  let onTop: boolean;
  let progressbar: number;


  $: onTop = scroll < 108 ? true : false;
  $: progressbar = scroll / totalHeight / 2;
</script>

<svelte:window 
  bind:scrollY={scroll}
  bind:outerHeight={totalHeight}
  ></svelte:window>

<nav class="big-nav" in:fly={{y:-20}} out:fly={{y:-100}}>
  <div class="container" >
    <div class="logo">
      <img src="./Logo.png" alt="">
      <div>
      <h1>ODRIOZOLA</h1>
      <p>ELECTROMECANICA</p>
      </div>
    </div>
    <div class="links">
      <ul>
        <li><a href="#quienessomos">NUESTRO TALLER</a></li>
        <li><a href="#servicios">SERVICIOS</a></li>
        <li><a href="#contacto">CONTACTO</a></li>
      </ul>
    </div>
  </div>
</nav>
{#if !(onTop)}
<nav class="small-nav" in:fly={{y:-20}}>
  <div class="container" >
    <div class="logo">
      <h1>ODRIOZOLA</h1>
    </div>
    <div class="small-links">
      <ul>
        <li><a href="#quienessomos">NUESTRO TALLER</a></li>
        <li><a href="#servicios">SERVICIOS</a></li>
        <li><a href="#contacto">CONTACTO</a></li>
      </ul>
    </div>
  </div>
  <div class="progressbar">
    <div style:transform={`scaleX(${progressbar})`}></div>
  </div>
</nav>
{/if}

<style>
  
nav {
  z-index: 10; 
}
.big-nav {
  position: absolute;
  z-index: 10;
  height: 108px;
  width: 100%;
  background: white;
  box-shadow: 0px 4px 16px rgb(10,10,10);
  padding-inline: 2%;
}
.small-nav{
  position: fixed;
  z-index: 8;
  height: 60px;
  width: 100%;
  background: white;
  box-shadow: 0px 4px 16px rgb(30,30,30);  
}

.small-nav h1 {
  font-size: 36px;
  margin-top: 9px;
}

.small-links a {
  padding: 21px 16px;
}

.container {
  display: flex;
  width: 100%;
  height: 100%;
  flex-direction: row;
  justify-content: space-between;
  padding-inline: 4px;
  padding-inline: 2%;
}

h1 {
  font-family: 'Krona One';
  letter-spacing: -4px;
  font-size: 48px;
  margin: 0 ;
}
.logo {
  display:flex;
  height: 100%;
  width: 25%;
}

.logo img {
  /* padding: 20px; */
  height: 116px;
  margin-right: 2px;
  margin-top: -3px;
}

.logo p {
  margin: 0;
  line-height: 6px;
  font-weight: 300;
  padding-left: 4px;
}

.logo div {
  padding: 16px 0;
}

.links {
  display:flex;
  height: 100%;
  width: 50%;
}

ul {
  display: flex;
  width: 100%;
  flex-direction: row;
  list-style: none;
  padding: 0;
  margin: 0;
  justify-content: end;
}

ul li {
  display: flex;
  justify-content: center;
  align-items: center;

}

ul li:hover {
  background: black;
}

ul li:hover a{
  color: white;
}

ul a {
  text-decoration: none;
  color: black;
  text-align: center;
  font-size: 16px;
  font-weight: 600;
  padding: 45px 30px;
  width: 100%;
}

.progressbar {
  position: relative;
  height: 4px;
  width: 100%;
  background: lightgray;

}

.progressbar div {
  position: relative;
  height: 4px;
  width: 100%;
  background: black;
  z-index: 10;
}

@media screen and (max-width: 950px) {
  .links{
    display: none;
  }
}
@media screen and (max-width: 800px) {

  nav {
    padding-inline: 0;
  }
  h1 {
    font-size: 2.2rem;
    margin-top: -4px;
  }
  .big-nav {
    height: 70px;
  }
  .container {
    justify-content: center;
  }
  .logo {
    width: auto;
    justify-content: center;
    align-items: center;
  }
  .logo img {
    height: 100%;
    margin-top: 4px;
  }
  .logo div {
    padding: 10px;
    margin-right: 3%;
  }
  .logo p {
    font-size: 1rem;
  }
  .links {
    display: none;
  }
  .small-nav {
    height: 46px;
  }
  .small-nav .logo {
    display: none;
  }
  .small-links ul li a{
    padding: 16px;
    font-size: 12px;
  }
}

</style>
