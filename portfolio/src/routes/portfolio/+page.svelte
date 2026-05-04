
<!-- 
    [] ADD LINKS to demos and repos
    [] Include Videos (Embedded) 
    [] That zooming shit when you click the pic
-->

<script lang="ts">
    import type { PageProps } from './$types';
    import Viewer from "$lib/components/Viewer.svelte";
    import MediaSlot from '$lib/components/MediaSlot.svelte';

    const filter_files = import.meta.glob<string>(
        '/src/lib/images/filter/*.png', { eager: true, query: '?url', import: 'default' }
    );

    let filter_links: string[] = Object.values(filter_files);

    const shrimp_files = import.meta.glob<string>(
        '/src/lib/images/shrimp/*.png', { eager: true, query: '?url', import: 'default' }
    );

    let shrimp_links: string[] = Object.values(shrimp_files);

    const cwn_files = import.meta.glob<string>(
        '/src/lib/images/cwn/*.png', { eager: true, query: '?url', import: 'default' }
    );

    let cwn_links: string[] = Object.values(cwn_files);

    let { data }: PageProps = $props();
</script>

<div class="gallery">
    <div class="entry">
        <Viewer model_path="/models/telemed.glb"/>
        <div class="datalog">
            <p>2025</p>
            <h2>TELEPALPATION</h2>
            <p>
                My Capstone Project during my bachelor's degree about teleoperated abdominal palpation.
                The idea is to make palpation more standardized and accessible to remote areas.
                I was responsible for:
            </p>
            <ul class="list-disc list-outside pl-5">
                <li>Robotic Path Planning</li>
                <li>Soft Tactile Sensor data acquisition</li>
                <li>Result Visualization</li>
            </ul>
        </div>
    </div>
    
    <div class="entry">
        <div class="datalog">
            <p>2026</p>
            <h2>BIOMIMETIC AIR FILTER</h2>
            <p>
                A conceptual design of a biomimetic air filtering system. The key aspects are as followed:
            </p>
            <ul class="list-disc list-outside pl-5">
                <li>Passive windflow tracking via Weather vane on positional encoder</li>
                <li>Helical path using centrifugal force to separate particles</li>
                <li>Wet and recirculating filtering agent for reusability</li>
            </ul>
        </div>
        <Viewer model_path="/models/filterhome.glb"/>
        <MediaSlot img_links={filter_links} />
    </div>
    <div class="entry">
        <MediaSlot img_links={shrimp_links} />
        <div class="datalog" style="text-align: center;">
            <p style="text-align: center;">2026</p>
            <h2>SHRIMP SIZE ESTIMATOR</h2>
            <p>
                A compact system which is comprised of:
            </p>
            <div style="justify-content: center;">
                <ul class="list-disc list-outside pl-5" style="text-align: left;">
                    <li>Tiny (510 KB) customized CNN for heatmap detection</li>
                    <li>Classical Computer Vision framework for real world size estimation</li>
                </ul>
            </div>
        </div>
        <Viewer model_path="/models/shrimp.glb"/>
    </div>
    <div class='entry'>
        <div class="datalog">
            <p>2024</p>
            <h2>INTERNSHIP PROJECTS</h2>
            <p>
                Works during internship
            </p>
            <ul class="list-disc list-outside pl-5">
                <li>Grade 1 Reading Test Platform : frontend and endpoint connections</li>
                <li>Parkinson's Disease Screening Application : hand tremor visualization</li>
            </ul>
        </div>
        <MediaSlot img_links={cwn_links} />
    </div>
</div>

<style>
    .gallery {
        display: flex;
        flex-direction: column;
        padding: 5rem;
        gap: 10vh; 
    }

    .entry {
        display: flex;
        flex-direction: row;
        justify-content: center; 
        align-items: center;    
        gap: 2rem;
        width: 100%;
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
        font-size: 42px;
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