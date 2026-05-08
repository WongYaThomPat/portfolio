<script lang="ts">
    import type { PageProps } from './$types';
    import { fade } from 'svelte/transition';
    let { data }: PageProps = $props();
</script>

<div class="timeline-wrapper" in:fade={{duration: 300}}>
    <div class="timeline-line"></div>
    
    <div class='main-container'>
        <div class='entry'>
            <img src="src/lib/images/ico/swu.png" alt="swu" class="logo">
            <p class='banner' style="background: hsl(7, 60%, 85%); color: #333;">
                Smart Global Science Major, <br>
                Satit Prasarnmit Demonstration School (Secondary) 
            </p>
            <div class='info'>
                <h3>2018 - 2021</h3>
                <p>GPAX : 3.92</p>
            </div>
        </div>

        <div class='entry'>
            <div class="logo-container">
                <img src="src/lib/images/ico/cwn-logo.png" alt="cwn" class="logo">
            </div>
            <p class='banner' style="background: hsl(141, 40%, 85%); color: #333;">
                Internship at Chanwanich co. ltd. <br> as Junior System Integrator
            </p>
            <div class='info'>
                <h3>June - July 2024</h3>
            </div>   
        </div>

        <div class='entry'>
            <img src="src/lib/images/ico/mahidol.png" alt="mahidol" class="logo">
            <p class='banner' style="background: hsl(219, 40%, 85%); color: #333;">
                Bachelor Degree in Biomedical Engineering, <br>
                Mahidol University 
            </p>
            <div class='info'>
                <h3>2021 - 2025</h3>
                <p>GPAX : 3.73 (First Class Honour)</p>
            </div>
        </div>
    </div>
</div>

<style>
    .timeline-wrapper {
        position: relative;
        width: 100%;
        display: flex;
        justify-content: center;
        padding: 40px 0;
        overflow-x: hidden;
    }

    .timeline-line {
        position: absolute;
        top: 50%;
        left: 0;
        width: 100%;
        height: 4px;
        background-color: #ccc;
        z-index: -1;
        transform: translateY(-50%);
    }

    .main-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        width: 100%;
        min-height: 65vh;
        gap: 2rem;
        padding: 0 2%;
    }

    .entry {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        max-width: 350px; 
        aspect-ratio: 1 / 1; 
        background-color: rgb(240, 240, 240);
        border-radius: 12px;
        transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        overflow: hidden;
    }

    @media (min-width: 1024px) {
        .entry:hover {
            transform: scale(1.15);
            z-index: 10;
        }
    }

    .logo {
        max-height: 80px;
        width: auto;
        margin-bottom: 15px;
    }

    .logo-container {
        margin: 16px;
    }

    .banner {
        text-align: center; 
        padding: 12px;
        margin: 0;         
        width: 100%;          
        box-sizing: border-box;
        font-weight: 600;
        font-size: 0.9rem;
    }

    .info {
        text-align: center;
        padding: 15px;
    }

    .info h3 {
        font-size: 1.2rem;
        margin-bottom: 5px;
    }

    @media (max-width: 1024px) {
        .timeline-line {
            display: none; 
        }

        .main-container {
            flex-direction: column;
            height: auto;
            gap: 40px;
        }

        .entry {
            aspect-ratio: auto;
            height: auto;
            max-width: 90%;
            padding-bottom: 20px;
        }
        
        .entry:hover {
            transform: translateY(-5px); 
        }
    }

    @media (max-width: 480px) {
        .banner {
            font-size: 0.8rem;
        }
    }
</style>