<script>
  $: showModal = false;

  const toggleModal = () => {
    showModal = !showModal;
  };

  const cssBlock = `#gradient-canvas {\nwidth: 100%;\nheight: 100%;\n--gradient-color-1: #161d22;\n--gradient-color-2: #6ec3f4;\n--gradient-color-3: #5c4c85;\n--gradient-color-4: #313ab9;\n}`;
  const htmlBlock = ` <canvas id="gradient-canvas" data-transition-in />`;
  const jsBlock = `import { Gradient } from './Gradient.js'\n\n// Create your instance\nconst gradient = new Gradient()\n\n// Call initGradient with the selector to your canvas\ngradient.initGradient('#gradient-canvas')`;
</script>

<!-- Trigger/Open The Modal -->
<button class="button-30" on:click={toggleModal}>Get Code</button>

<div class="modal" class:hideModal={!showModal}>
  <!-- Modal content -->
  <div class="modal-content">
    <span class="close" on:click={toggleModal}>&times;</span>
    <div>
      <p class="info">
        Download the <a
          target="_blank"
          href="https://gist.github.com/VithuJey/186daf9efa936fc065b6dbc8f6ab3914"
          >Gradient.js</a
        > file and add in your project
      </p>
      <p class="sub-title">HTML</p>
      <pre>{htmlBlock}</pre>
      <p class="sub-title">CSS</p>
      <pre>{cssBlock}</pre>
      <p class="sub-title">JS</p>
      <pre>{jsBlock}</pre>
    </div>
  </div>
</div>

<style>
  .modal {
    display: block;
    position: fixed;
    z-index: 1;
    padding-top: 140px;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgb(0, 0, 0);
    background-color: rgba(0, 0, 0, 0.4);
    /* border: 1px solid black; */
    border-radius: 10px;
  }

  .hideModal {
    display: none;
  }

  .modal-content {
    background-color: #fefefe;
    margin: auto;
    padding: 20px;
    border: 1px solid #888;
    width: 60%;
  }

  .close {
    color: #000;
    float: right;
    font-size: 28px;
    font-weight: bold;
  }

  .close:hover,
  .close:focus {
    color: rgb(85, 85, 85);
    text-decoration: none;
    cursor: pointer;
  }

  pre {
    background-color: #e1e1e1;
    padding: 20px;
    border-radius: 10px;
    font-size: 14px;
  }

  .info {
    text-align: center;
  }

  .sub-title {
    font-size: 20px;
  }

  .button-30 {
    align-items: center;
    appearance: none;
    background-color: #fcfcfd;
    border-radius: 4px;
    border-width: 0;
    box-shadow: rgba(45, 35, 66, 0.4) 0 2px 4px,
      rgba(45, 35, 66, 0.3) 0 7px 13px -3px, #d6d6e7 0 -3px 0 inset;
    box-sizing: border-box;
    color: #36395a;
    cursor: pointer;
    display: inline-flex;
    font-family: "Roboto Mono", monospace;
    height: 48px;
    justify-content: center;
    line-height: 1;
    list-style: none;
    overflow: hidden;
    padding-left: 16px;
    padding-right: 16px;
    position: relative;
    text-align: left;
    text-decoration: none;
    transition: box-shadow 0.15s, transform 0.15s;
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
    white-space: nowrap;
    will-change: box-shadow, transform;
    font-size: 18px;
  }

  .button-30:focus {
    box-shadow: #d6d6e7 0 0 0 1.5px inset, rgba(45, 35, 66, 0.4) 0 2px 4px,
      rgba(45, 35, 66, 0.3) 0 7px 13px -3px, #d6d6e7 0 -3px 0 inset;
  }

  .button-30:hover {
    box-shadow: rgba(45, 35, 66, 0.4) 0 4px 8px,
      rgba(45, 35, 66, 0.3) 0 7px 13px -3px, #d6d6e7 0 -3px 0 inset;
    transform: translateY(-2px);
  }

  .button-30:active {
    box-shadow: #d6d6e7 0 3px 7px inset;
    transform: translateY(2px);
  }
</style>
