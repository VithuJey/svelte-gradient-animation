<script>
  import Gradient from "./components/Gradient.svelte";
  import Controller from "./components/Controller.svelte";
</script>

<main>
  <div class="flex-container">
    <div class="flex-item-left">
      <Gradient />
    </div>
    <div class="flex-item-right">
      <Controller />
    </div>
  </div>
  <div class="footer">
    Thanks to <a href="https://stripe.com/">Stripe</a> ~ Designed by
    <a href="https://medium.com/@vithushjeytharma">Vithu</a>
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

  @media only screen and (max-width: 600px) {
    .flex-container {
      padding: 10px;
    }
    .flex-item-left {
      padding-bottom: 10px;
    }
    .footer {
      width: 100%;
      text-align: center;
    }
  }

  @media only screen and (min-width: 600px) {
    .flex-container {
      display: flex;
      flex-direction: column;
      height: 100%;
      padding: 10px;
    }

    .flex-item-left {
      flex: 70%;
      padding-bottom: 10px;
    }

    .flex-item-right {
      flex: 30%;
    }

    .footer {
      width: auto;
      text-align: center;
    }
  }

  @media only screen and (min-width: 992px) {
    .flex-container {
      display: flex;
      flex-direction: row;
      height: 100vh;
      padding: 0;
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

    .footer {
      position: absolute;
      bottom: 5px;
      left: 40%;
      width: auto;
    }
  }
</style>
