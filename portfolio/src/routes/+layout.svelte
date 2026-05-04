<script lang="ts">
	import './layout.css';

	let name = "WONGSAPAT THOMYA";
    let letters = name.split('');

	let { children } = $props();
</script>

<!-- <svelte:head><link rel="icon" href={favicon} /></svelte:head> -->

<div class="index">
	<h1>
		{#each letters as char}
        	<span class="letter">{char === ' ' ? '\u00A0' : char}</span>
		{/each}
	</h1>
    
	<div class='links'>
		<a 
			href="https://github.com/WongYaThomPat"
			target="_blank" 
			rel="noopener noreferrer"
		>
			Github
		</a>
		<a 
			href="contact"
		>
			Contact Me
		</a>
		<a href="/resume/WT_RESUME.pdf" download>
			Download Resume
		</a>
	</div>
</div>
<nav class='navbar'>
	<a href="about">About</a>
	<a href="portfolio">Portfolio</a>
	<a href="education">Education / Experience</a>
	<a href="contact">Contact</a>
</nav>

<style>
    .index {
		padding-left: 2vw;
        display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		background: #242424;
    }

	.index h1 {
        font-weight: 700; 
        font-size: 80px;
        letter-spacing: 2px;  
    	color: #e8fff6;
        display: flex; 
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
		flex-direction: row;
		align-items: center;
		justify-content: space-evenly;
		padding-right: 2vw;
		color: white;
		gap: 1vw;
	}

	.links a {
		transition: transform 0.2s ease, color 0.2s ease;
	}

	.links a:hover {
		font-size: 150%;
		color:#e8fff6;
	}

	.navbar {
		justify-content: space-evenly;
		padding: 20px;
		display: flex;     
		gap: 10px;         
		background: #333;   
	}

	.navbar a {
		flex: 1;
		display: block;     
		padding: 10px 20px;  
		background: #555;   
		color: white;
		text-decoration: none;
		border-radius: 4px;  
		transition: transform 0.2s ease, color 0.2s ease;
	}

	.navbar a:hover {
		background: #22b37b;
	}

</style>

{@render children()} 
