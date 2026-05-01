<script lang='ts'>
  import { T } from '@threlte/core';
  import { GLTF, OrbitControls } from '@threlte/extras';

  let { model_path }: { model_path : string } = $props();

</script>

<T.AmbientLight intensity={0.5} />

<T.DirectionalLight 
  position={[5, 10, 5]} 
  intensity={4} 
  castShadow 
/>

<T.PerspectiveCamera makeDefault position={[10, 10, 10]} />
<OrbitControls 
  enableDamping 
  autoRotate={true} 
  autoRotateSpeed={2} 
/>

<GLTF url={model_path} />