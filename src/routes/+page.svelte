<script lang="ts">
	import Hero from '$lib/components/Hero.svelte';
	import Skills from '$lib/components/Skills.svelte';
	import Portfolio from '$lib/components/Portfolio.svelte';
	import Contact from '$lib/components/Contact.svelte';
	import ThemeToggle from '$lib/components/ThemeToggle.svelte';
</script>

<svelte:head>
	<title>Andreas - Senior Software Engineer | Fullstack Developer</title>
	<meta name="description" content="Senior Software Engineer with strong focus on frontend development. Specialized in React, Node.js, and modern web technologies." />
</svelte:head>

<main class="min-h-screen">
	<ThemeToggle />
	<Hero />
	<Skills />
	<Portfolio />
	<Contact />
</main>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}
</style>
