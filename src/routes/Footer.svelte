<script lang="ts">

</script>

<footer>
  <div class="block">
  <div class="logo">
    <img src="./Logo.png" alt="">
    <h2>ODRIOZOLA</h2>
  </div>

  <ul>
    <li><a href="https://maps.app.goo.gl/5R58TeTCN3qBPuaj6">Los Jazmines 6005, Colastine Norte</a></li>
    <li><a href="https://wa.link/my4ams">+543425082986</a></li>
    <li><a href="mailto:abc@example.com">r.odriozola.520@gmail.com</a></li>
  </ul>
  </div>
  <div class="block">
    <p>ACCESOS RAPIDOS</p>
    <ul>
      <li><a href="#quienessomos">Nuestro Taller</a></li>
      <li><a href="#servicios">Servicios</a></li>
      <li><a href="#contacto">Contacto</a></li>
    </ul></div>
  <div class="copy">	<p>EMI &copy {new Date().getFullYear()}</p></div>
</footer>

<style>
  


  footer {
    height: 100%;
    background: #303030;
    display: flex;
    padding: 20px;
    color: #C0C0C0;
  }

  .logo {
    width: 320px;
    display: flex;
    align-items: center;
  }

  .block  {
    display: inline-block;
    height: 100%;
    border-right: 2px solid #707070;
    padding-inline: 40px;
    align-self: center;
  }


  img {
    width: 25%;
    display:inline-flex;
    filter: invert(80%);
  }

  h2 {
    font-family: 'Krona One';
  letter-spacing: -4px;
  font-size: 2rem;
  margin: 0 ;
  }

  ul {
    list-style: none;
    padding: 0;
    margin-top: 0;
  }

  a {
    text-decoration: none;
    color: #707070;
  }
  a:hover {
    text-decoration: underline;
  }

  .copy {
    display: flex;
    width: 30%;
    align-items: end;
    justify-content: end;
  }
  .copy p {
    margin: 0;
    color: #707070;
  }

@media screen and (max-width: 800px) {

  .block {
    border-right: none;
    display: block;
    padding-inline: 16px;
    align-self: self-start;
  }
  footer {
    flex-direction: column;

  }
  .copy {
    align-self: end;
  }
}

</style>