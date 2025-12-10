<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { Github, Linkedin, Mail } from 'lucide-svelte';
</script>

<section class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-background via-background to-secondary/20">
	<div class="container px-4 md:px-6">
		<div class="flex flex-col items-center space-y-8 text-center">
			<div class="space-y-4 max-w-3xl">
				<h1 class="text-4xl font-bold tracking-tighter sm:text-5xl md:text-6xl lg:text-7xl bg-gradient-to-r from-primary to-primary/60 bg-clip-text text-transparent animate-in fade-in slide-in-from-bottom-4 duration-1000">
					Senior Software Engineer
				</h1>
				<h2 class="text-2xl sm:text-3xl md:text-4xl font-semibold text-foreground/80 animate-in fade-in slide-in-from-bottom-4 duration-1000 delay-150">
					Fullstack Developer
				</h2>
				<p class="text-lg sm:text-xl md:text-2xl text-muted-foreground animate-in fade-in slide-in-from-bottom-4 duration-1000 delay-300">
					Strong Focus on <span class="text-primary font-semibold">Frontend Development</span>
				</p>
			</div>
			
			<div class="flex flex-col sm:flex-row gap-4 animate-in fade-in slide-in-from-bottom-4 duration-1000 delay-500">
				<Button size="lg" on:click={() => document.getElementById('portfolio')?.scrollIntoView({ behavior: 'smooth' })}>
					View Portfolio
				</Button>
				<Button size="lg" variant="outline" on:click={() => document.getElementById('contact')?.scrollIntoView({ behavior: 'smooth' })}>
					Contact Me
				</Button>
			</div>

			<div class="flex gap-4 animate-in fade-in slide-in-from-bottom-4 duration-1000 delay-700">
				<Button variant="ghost" size="icon" href="https://github.com/isandreas" target="_blank" rel="noopener noreferrer">
					<Github class="h-5 w-5" />
					<span class="sr-only">GitHub</span>
				</Button>
				<Button variant="ghost" size="icon" href="https://linkedin.com/in/yourprofile" target="_blank" rel="noopener noreferrer">
					<Linkedin class="h-5 w-5" />
					<span class="sr-only">LinkedIn</span>
				</Button>
				<Button variant="ghost" size="icon" href="mailto:your.email@example.com">
					<Mail class="h-5 w-5" />
					<span class="sr-only">Email</span>
				</Button>
			</div>
		</div>
	</div>

	<!-- Scroll indicator -->
	<div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
		<svg class="w-6 h-6 text-muted-foreground" fill="none" stroke="currentColor" viewBox="0 0 24 24">
			<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
		</svg>
	</div>
</section>
