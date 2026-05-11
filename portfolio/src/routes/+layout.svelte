<script lang="ts">
    import './layout.css';

    const logo : string = '/ghlg.jpg'
    let name = "WONGSAPAT THOMYA";
    let letters = name.split('');

    let { children } = $props();
</script>

<svelte:head>
    <link rel="icon" href={logo} />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<div class="page-container">
    <header class="index header-container">
        <h1 class="name-display">
            {#each letters as char}
                <span class="letter">{char === ' ' ? '\u00A0' : char}</span>
            {/each}
        </h1>
        
        <div class='links'>
            <a href="contact">Contact Me</a>
            <a href="/pdf/WT_RESUME.pdf" download>Download Resume</a>
        </div>
    </header>

    <nav class='navbar'>
        <a href="/">Home</a>
        <a href="about">About</a>
        <a href="portfolio">Portfolio</a>
        <a href="education">Education / Experience</a>
    </nav>

    <main class="content-area">
        {@render children()} 
    </main>

    <footer class='index footer'>
        <p>© 2026 Wongsapat Thomya. All rights reserved.</p>
    </footer>
</div>

<style>
    .page-container {
        display: flex;
        flex-direction: column;
        min-height: 100vh;
    }

    .content-area {
        flex-grow: 1;
    }

    .index {
        padding: 2rem 5vw;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        background: #242424;
        color: #e8fff6;
        flex-wrap: wrap;
        gap: 20px;
    }

    .name-display {
        font-weight: 700;
        font-size: clamp(1.5rem, 7vw, 80px); 
        letter-spacing: 2px;
        display: flex;
        flex-wrap: wrap; 
        line-height: 1.2;
        margin: 0;
    }

    .letter {
        display: inline-block;
        transition: transform 0.2s ease, color 0.2s ease;
        cursor: default;
    }

    .letter:hover {
        text-transform: lowercase; 
        color: #414141;
        transform: translateY(-5px);
    }

    .links {
        display: flex;
        gap: 20px;
    }

    .links a {
        transition: transform 0.2s ease, color 0.2s ease;
        white-space: nowrap;
        text-decoration: underline;
        color: white;
    }

    .links a:hover {
        transform: scale(1.1); 
        color: #e8fff6;
    }

    /* Navbar */
    .navbar {
        display: flex;     
        justify-content: space-evenly;
        padding: 15px;
        gap: 10px;         
        background: #333;   
    }

    .navbar a {
        flex: 1;
        text-align: center;
        padding: 12px 10px;  
        background: #555;   
        color: white;
        text-decoration: none;
        border-radius: 4px;  
        transition: background-color 0.2s ease;
    }

    .navbar a:hover {
        background: #22b37b; 
    }

    .footer {
        justify-content: center;
        min-height: auto;
        padding: 4% 2%;
    }

    @media (max-width: 768px) {
        .index {
            flex-direction: column;
            text-align: center;
            padding: 40px 20px;
        }

        .name-display {
            justify-content: center;
        }

        .links {
            justify-content: center;
            width: 100%;
        }

        .navbar {
            flex-direction: column;
        }
    }
</style>