<script>
  import { ColorsStore } from "../store/Colors";
  import { PaletteStore } from "../store/Palette";
  import { get } from "svelte/store";
  import Modal from "./Modal.svelte";

  const colorSet = get(ColorsStore);
  $: [color1, color2, color3, color4] = Object.values(colorSet);

  const paletteSet = get(PaletteStore);

  $: selectedPaletteIndex = 0;

  $: ColorsStore.set({
    color1: color1,
    color2: color2,
    color3: color3,
    color4: color4,
  });

  const togglePalette = (index) => {
    if (index !== selectedPaletteIndex) {
      selectedPaletteIndex = index;
      const newColorSet = {
        color1: paletteSet[index].color1,
        color2: paletteSet[index].color2,
        color3: paletteSet[index].color3,
        color4: paletteSet[index].color4,
      };

      [color1, color2, color3, color4] = Object.values(newColorSet);
      ColorsStore.set(newColorSet);
    }
  };
</script>

<div class="container col">
  <div class="title">Gradient Animation</div>
  <div class="col col-gap">
    <div class="row row-gap">
      <input class="input-color" type="color" bind:value={color1} />
      <div class="hexcode">{color1.toUpperCase()}</div>
    </div>
    <div class="row row-gap">
      <input class="input-color" type="color" bind:value={color2} />
      <div class="hexcode">{color2.toUpperCase()}</div>
    </div>
    <div class="row row-gap">
      <input class="input-color" type="color" bind:value={color3} />
      <div class="hexcode">{color3.toUpperCase()}</div>
    </div>
    <div class="row row-gap">
      <input class="input-color" type="color" bind:value={color4} />
      <div class="hexcode">{color4.toUpperCase()}</div>
    </div>
  </div>
  {#each paletteSet as palette, index}
    <div class="col" on:click={() => togglePalette(index)}>
      <div
        class="palette row row-gap"
        class:selected={index === selectedPaletteIndex}
      >
        <div
          class="col palette-col"
          style="background-color: {palette.color1}"
        />
        <div
          class="col palette-col"
          style="background-color: {palette.color2}"
        />
        <div
          class="col palette-col"
          style="background-color: {palette.color3}"
        />
        <div
          class="col palette-col"
          style="background-color: {palette.color4}"
        />
      </div>
    </div>
  {/each}

  <Modal />
</div>

<style>
  .container {
    background-color: #fff;
    height: 100%;
    border-radius: 20px;
    padding-left: 20px;
    padding-right: 20px;
    box-shadow: 18px 18px 29px -5px rgba(0, 0, 0, 0.1);
  }

  .title {
    font-size: 20px;
    text-align: center;
  }

  .col {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .row {
    display: flex;
    flex-direction: row;
    align-items: center;
  }

  .col-gap {
    margin-top: 20px;
    margin-left: 20px;
  }

  .row-gap {
    margin-bottom: 20px;
  }

  .input-color {
    width: 70px;
    height: 50px;
    background-color: white;
    border: 1px solid rgb(192, 192, 192);
    cursor: pointer;
  }

  .hexcode {
    font-size: 18px;
    color: #48494b;
    margin-left: 60px;
  }

  .palette {
    height: 60px;
    cursor: pointer;
  }

  .selected {
    outline: 4px solid rgba(0, 255, 85, 0.6);
    border: 1px solid rgb(255, 255, 255);
  }

  .palette-col {
    width: 25%;
    height: 100%;
    background-color: rgb(0, 224, 75);
  }

  @media only screen and (min-width: 992px) {
    .title {
      font-size: 24px;
      text-align: center;
    }

    .col-gap {
      margin-top: 25px;
      margin-left: 25px;
    }

    .row-gap {
      margin-bottom: 25px;
    }
  }

  @media only screen and (min-width: 1600px) {
    .title {
      font-size: 36px;
      text-align: center;
    }

    .col-gap {
      margin-top: 30px;
      margin-left: 30px;
    }

    .row-gap {
      margin-bottom: 30px;
    }
  }
</style>
