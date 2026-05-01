<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<div class="index">
    <h1>WONGSAPAT THOMYA</h1>
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
        display: block;
		background: #c4c4c4;
    }

	.index h1 {
		font-family: 'Arial Narrow', sans-serif; 
		font-weight: 700; 
        font-size: 80px;
		letter-spacing: 2px;  
        color:Grey
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
	}

	.navbar a:hover {
		background: #b32272;
	}

</style>

{@render children()} 
