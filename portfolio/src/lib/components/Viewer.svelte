<script lang="ts">
    import { Canvas } from "@threlte/core"; 
    import { T } from '@threlte/core';
    import { GLTF, OrbitControls } from '@threlte/extras';
    let { model_path }: { model_path : string } = $props();
</script>

<div class='canvas-container'>
    <Canvas>
        <T.AmbientLight intensity={0.5} />

    <T.DirectionalLight 
        position={[5, 10, 5]} 
        intensity={6} 
        castShadow 
    />

    <T.PerspectiveCamera makeDefault position={[11, 11, 11]} />
    <OrbitControls 
        enableDamping={true}
        enableZoom={false}
        autoRotate={true} 
        autoRotateSpeed={1} 
    />

    <GLTF url={model_path} position={[0, 0, 0]}/>
    </Canvas>
</div>


<style>
    .canvas-container {
        height: 35vh;
        width: auto;
        cursor: pointer;
        /* margin: 10px ; */
        /* background-color: aquamarine;
        border-radius: 20%; */
    }
</style>