<script>
  import { onMount } from "svelte";
  import Gradient from "../utils/Gradient";
  import { ColorsStore } from "../store/Colors";

  let colorSet;

  const gradient = new Gradient();
  onMount(() => {
    // subscribe store
    const unsubscribe = ColorsStore.subscribe((value) => {
      colorSet = { ...value };
      // init gradient
      gradient.initGradient("#gradient-canvas");
    });

    // unsubscribe store on unmount
    return () => unsubscribe();
  });
</script>

<canvas
  id="gradient-canvas"
  style="width: 100%; height: 100%;
      border-radius: 20px;
      --gradient-color-1:{colorSet?.color1}; 
      --gradient-color-2: {colorSet?.color2};
      --gradient-color-3: {colorSet?.color3};
      --gradient-color-4: {colorSet?.color4};"
  data-transition-in
/>

<style>
  #gradient-canvas {
    box-shadow: 18px 18px 29px -5px rgba(0, 0, 0, 0.1);
  }
</style>
