<script lang="ts">

</script>

<footer>
  <div>
  <div class="block">
  <div class="logo">
    <img src="./Logo.png" alt="Logo de la marca">
    <h2>ODRIOZOLA</h2>
  </div>

  <ul>
    <li><a href="https://maps.app.goo.gl/5R58TeTCN3qBPuaj6">Los Jazmines 6005, Colastine Norte</a></li>
    <li><a href="https://wa.link/my4ams">+543425082986</a></li>
    <li><a href="mailto:abc@example.com">r.odriozola.520@gmail.com</a></li>
  </ul>
  </div>
</div>
  <div class="copy">	<p>EMI &copy {new Date().getFullYear()}</p></div>
</footer>

<style>
  


  footer {
    height: 100%;
    background: #303030;
    display: flex;
    padding: 20px;
    color: #C0C0C0;
    justify-content: space-between;
  }

  .logo {
    width: 250px;
    display: flex;
    align-items: center;
  }

  .block  {
    display: inline-block;
    height: auto;
    border-right: 2px solid #707070;
    padding-inline: 40px;
    align-self: center;
  }


  img {
    width: 90px;
    display:inline-flex;
    filter: invert(80%);
  }

  h2 {
    font-family: 'Krona One';
  letter-spacing: -4px;
  font-size: 1.4rem;
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
    width: auto;
    align-items: end;
    align-self: flex-end;
    justify-content: end;
    margin-block: 12px ;
  }
  .copy p {
    width: 100%;
    margin: 0;
    color: #707070;
    text-align: end;
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