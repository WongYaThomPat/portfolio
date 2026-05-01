<script lang="ts">
    import type { PageProps } from './$types';
    import Viewer from "$lib/components/Viewer.svelte";
    let { data }: PageProps = $props();
</script>

<div class="gallery">
    <div class="entry">
        <Viewer model_path="/models/telemed.glb"/>
        <div class="datalog">
            <h2>TELEPALPATION</h2>
            <p>
                Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
                It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
            </p>
        </div>
    </div>
    <div class="entry">
        <div class="datalog">
            <h2>PASSIVE AIR FILTER</h2>
            <p>
                Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
                It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
            </p>
        </div>
        <Viewer model_path="/models/filterhome.glb"/>
    </div>
    <div class="entry">
        <Viewer model_path="/models/shrimp.glb"/>
        <div class="datalog">
            <h2>SHRIMP SIZE ESTIMATOR</h2>
            <h3>fix model texture!!!</h3>
            <p>
                Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
                It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
            </p>
        </div>
    </div>
    
</div>

<style>
    .gallery {
        display: flex;
        flex-direction: column;
        gap: 1vh; 
    }

    .entry {
        display: flex;
        flex-direction: row;
        justify-content: center; 
        align-items: center;    
        gap: 1rem;
        width: 100%;
        padding: 2rem;
    }

    .entry p {
        text-align: justify;
    }

    .entry > :global(*) {
        flex: 1;           
        max-width: 600px;  
    }

    .datalog {
        line-height: 1.6;
    }

    .datalog h2 {
        font-size: 24px;
    }

    @media (max-width: 768px) {
        .entry {
            flex-direction: column; 
        }
        
        .entry > :global(*) {
            width: 100%; 
        }
    }
</style>