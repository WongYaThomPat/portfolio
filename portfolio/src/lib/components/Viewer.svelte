<script lang="ts">
    import { Canvas } from "@threlte/core"; 
    import Scene from "$lib/model/Scene.svelte";

    let { model_path }: { model_path : string } = $props();
</script>

<div class='canvas-container'>
    <Canvas>
        <Scene model_path={model_path} />
    </Canvas>
</div>


<style>
    .canvas-container {
        height: 40vh;
        width: 20vw;
    }
</style>