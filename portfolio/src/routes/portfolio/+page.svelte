<script lang="ts">
    import type { PageProps } from './$types';
    import { fade } from 'svelte/transition';
    import Viewer from "$lib/components/Viewer.svelte";
    import MediaSlot from '$lib/components/MediaSlot.svelte';
    import TechBanner from '$lib/components/TechBanner.svelte';

    const shrimp_files = import.meta.glob<string>(
        '/src/lib/images/shrimp/*.png', { eager: true, query: '?url', import: 'default' }
    );

    let shrimp_links: string[] = Object.values(shrimp_files);

    const filter_files = import.meta.glob<string>(
        '/src/lib/images/filter/*.png', { eager: true, query: '?url', import: 'default' }
    );

    let filter_links: string[] = Object.values(filter_files);

    const cwn_files = import.meta.glob<string>(
        '/src/lib/images/cwn/*.png', { eager: true, query: '?url', import: 'default' }
    );

    let cwn_links: string[] = Object.values(cwn_files);

    const telemed_files = import.meta.glob<string>(
        '/src/lib/images/telemed/*.png', { eager: true, query: '?url', import: 'default' }
    );

    let telemed_links: string[] = Object.values(telemed_files);

    let { data }: PageProps = $props();
</script>

<div in:fade={{duration: 300}} class="gallery">
    <div class="entry">
        <Viewer model_path="/models/telemed.glb"/>
        <div class="datalog">
            <p>2024 - 2025</p>
            <h2>TELEPALPATION</h2>
            <TechBanner tools={[
                "OpenCV", "Scikit-learn", "Open3D", 
                "MATLAB", "Arduino IDE", "RealSense-SDK", 
                "Xarm-SDK", "Autodesk Fusion", "Overleaf Latex"]} 
            />
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
            <div class='extras'>
                <p>:</p>
                <a href="https://youtu.be/ltIazuCAJnQ" 
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Probe-Video
                </a>
                <a href="https://youtu.be/kmPaTpRiduY" 
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Robot-Video
                </a>
                <a href="https://drive.google.com/file/d/1nZQrSGE8SvZNcedhNtM9q7Z-PEbdyv4e/view?usp=drive_link" 
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Full Thesis
                </a>
                <a href="https://github.com/WongYaThomPat/TELEPALPATION"
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Github
                </a>
            </div>
        </div>
        <MediaSlot img_links={telemed_links} />
    </div>
    <div class="entry">
        <Viewer model_path="/models/shrimp.glb"/>
        <div class="datalog">
            <p>2026</p>
            <h2>SHRIMP SIZE ESTIMATOR</h2>
            <TechBanner tools={["OpenCV", "Pytorch", "Scikit-learn", "Blender"]} />
            <p>
                In shrimp harvesting, excessive handling can indirectly lead to stunted growth. 
                Thus, I designed a compact non-invasive workflow which is comprised of:
            </p>
            <ul class="list-disc list-outside pl-5" style="text-align: left;">
                <li>Tiny customized CNN for heatmap detection</li>
                <li>Classical Computer Vision framework for real world size estimation</li>
            </ul>
            <p style="margin-top:10px">The final results are:</p>
            <ul class="list-disc list-outside pl-5" style="text-align: left;">
                <li>Precision: 1.00 | Recall: 0.99 | F1: 1.00</li>
                <li>Median Length Error: 4.65% | Median Diameter Error: 4.52%</li>
                <li>Model Size: 510 KB</li>
            </ul>
            <div class='extras'>
                <p>:</p>
                <a href="https://drive.google.com/drive/folders/1aER88x9KMSNKa5AhA5u5pG1JIvS6Qcnq?usp=drive_link"
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Train Dataset
                </a>
                <a href="https://github.com/WongYaThomPat/ShrimpEstimator" 
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Github
                </a>
            </div>
        </div>
        <MediaSlot img_links={shrimp_links} />
    </div>
    <div class="entry">
        <Viewer model_path="/models/filterhome.glb"/>
        <div class="datalog">
            <p>2026</p>
            <h2>BIOMIMETIC AIR FILTER</h2>
            <TechBanner tools={["Blender", "Godot Engine"]} />
            <p>
                A conceptual design of a biomimetic air filtering system, because HEPA filters
                eventually get blocked and need to be discarded and replaced. 
                The key aspects are as followed:
            </p>
            <ul class="list-disc list-outside pl-5">
                <li>Passive windflow tracking via Weather vane on positional encoder</li>
                <li>Helical path using centrifugal force to separate particles</li>
                <li>Wet and recirculating filtering agent for reusability</li>
            </ul>
            <div class='extras'>
                <p>:</p>
                <a href="https://youtu.be/HsOemdrmEyc" 
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Video Demo
                </a>
                <a href="https://drive.google.com/file/d/1pWZCGJ2JlZPymytVU9lwRPtNz9Zs4-eg/view?usp=drive_link" 
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Download Zip
                </a>
            </div>
        </div>
        <MediaSlot img_links={filter_links} />
    </div>
    <div class='entry'>
        <div class="datalog">
            <p>2024</p>
            <h2>INTERNSHIP PROJECTS</h2>
            <TechBanner tools={["React", "Postman"]} />
            <p>
                Works during internship
            </p>
            <ul class="list-disc list-outside pl-5">
                <li>Grade 1 Reading Test Platform : frontend and endpoint connections</li>
                <li>Parkinson's Disease Screening Application : hand tremor visualization</li>
            </ul>
            <div class='extras'>
                <p>:</p>
                <a href="https://youtu.be/bkgVxLS7qmQ" 
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Video Demo
                </a>
                <a href="https://github.com/WongYaThomPat/pd-handTremor-demo"
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Github-Hand
                </a>
            </div>
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

    .extras {
        margin: 30px;
        display: flex;
        flex-direction: row;
        justify-content: end;
        align-items: center;
        gap: 10px;
    }

    .extras > a {
        background-color: black;
        color: white;
        padding: 10px;
        border-radius: 8px;
    }

    .extras > a:hover {
        opacity: 70%;
    }

    .entry {
        display: flex;
        flex-direction: row;
        justify-content: center; 
        align-items: center;    
        gap: 0;
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
            gap: 50px;
        }
        
        .entry > :global(*) {
            width: 100%; 
        }

        .entry {
            margin-top: 60px;
        }
    }
</style>