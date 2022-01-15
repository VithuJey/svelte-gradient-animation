<script>
  import Gradient from "./components/Gradient.svelte";
  import Controller from "./components/Controller.svelte";
</script>

<main>
  <div class="flex-container">
    <div class="flex-item-left">
      <Gradient />
      <div class="footer">
        Thanks to <a href="https://stripe.com/">Stripe</a> ~ Designed by
        <a href="https://medium.com/@vithushjeytharma">Vithu</a>
      </div>
    </div>
    <div class="flex-item-right">
      <Controller />
    </div>
  </div>
</main>

<style>
  :root {
    font-family: "Roboto Mono", monospace;
  }

  main {
    background-color: #e1e1e1;
    min-height: 100vh;
  }

  .footer {
    text-align: center;
  }

  @media only screen and (min-width: 600px) and (max-width: 600px) {
    .flex-container {
      display: flex;
      flex-direction: column;
      width: 100vw;
      height: 100vh;
    }

    .flex-item-left {
      padding-left: 40px;
      padding-right: 20px;
      padding-top: 40px;
      padding-bottom: 40px;
      flex: 70%;
    }

    .flex-item-right {
      padding-left: 20px;
      padding-right: 40px;
      padding-top: 40px;
      padding-bottom: 40px;
      flex: 30%;
    }
  }

  @media only screen and (min-width: 992px) {
    .flex-container {
      display: flex;
      flex-direction: row;
      width: 100vw;
      height: 100vh;
    }

    .flex-item-left {
      padding-left: 40px;
      padding-right: 20px;
      padding-top: 40px;
      padding-bottom: 40px;
      flex: 70%;
    }

    .flex-item-right {
      padding-left: 20px;
      padding-right: 40px;
      padding-top: 40px;
      padding-bottom: 40px;
      flex: 30%;
    }
  }
</style>
