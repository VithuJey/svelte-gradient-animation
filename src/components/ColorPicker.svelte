<script>
  import { ColorsStore } from "../store/Colors";
  import { get } from "svelte/store";

  import HsvPicker from "./HsvPicker.svelte";

  export let color;
  let showPicker = false;

  let colorSet = get(ColorsStore);

  const toggleColorPicker = () => {
    showPicker = !showPicker;
  };

  function onColorChange(hex) {
    console.log(hex.detail);
    color = hex.detail;
    ColorsStore.set({ ...colorSet, color1: color });
  }
</script>

<button
  style=" width: 40px; height: 40px; border-radius: 10px; border-color: black; border-width: 0px; background-color: {color};"
  on:click={toggleColorPicker}
/>

{#if showPicker}
  <HsvPicker on:hexColorChange={onColorChange} startColor={color} />
{/if}
