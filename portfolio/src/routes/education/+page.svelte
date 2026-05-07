<script lang="ts">
    import type { PageProps } from './$types';
    import { fade } from 'svelte/transition';
    let { data }: PageProps = $props();
</script>

<div class="timeline-wrapper" in:fade={{duration: 300}}>
    <div class="timeline-line"></div>
    <div class='main-container'>
        <div class='entry'>
            <img src="src/lib/images/ico/swu.png" alt="swu">
            <p class='banner' 
                style="background: hsl(7, 60%, 85%); color: #333;" 
            >
                Smart Global Science Major, 
                Satit Prasarnmit Demonstration School (Secondary) 
            </p>
            <div class='info'>
                <h3 class='text-4xl'>2018 - 2021</h3>
                <p>GPAX : 3.92</p>
            </div>
        </div>

        <div class='entry'>
            <div style="margin: 16px;">
                <img src="src/lib/images/ico/cwn-logo.png" alt="cwn">
            </div>
            <p class='banner' 
                style="background: hsl(141, 40%, 85%); color: #333;" 
            >
                Internship at Chanwanich co. ltd. as Junior System Integrator
            </p>
            <div class='info'>
                <h3 class='text-3xl'>June - July 2024</h3>
            </div>   
        </div>

        <div class='entry'>
            <img src="src/lib/images/ico/mahidol.png" alt="mahidol">
            <p class='banner' 
                style="background: hsl(219, 40%, 85%); color: #333;"
            >
                Bachelor Degree in Biomedical Engineering,
                Mahidol University 
            </p>
            <div class='info'>
                <h3 class='text-4xl'>2021 - 2025</h3>
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
        justify-content: space-around;
        align-items: center;
        width: auto;
        height: 65vh;
        margin: 1%;
    }

    .entry {
        align-items: center;
        justify-content: center;
        display: flex;
        flex-direction: column;
        width: 400px;
        height: 400px;
        margin: 5%;
        background-color: rgb(240, 240, 240);
        border-radius: 2%;
        transition: all 0.3s ease;
    }

    .entry:hover {
        height: 600px;
        width: 600px;
    }

    .banner {
        color: aliceblue; 
        text-align: center; 
        padding:5px;
        margin: 0;        
        width: 100%;          
        box-sizing: border-box;
    }

    .info {
        text-align: center;
        padding: 5%;
    }

</style>