<script lang="ts">
	import { Card, CardContent, CardDescription, CardHeader, CardTitle } from '$lib/components/ui/card';
	import { Badge } from '$lib/components/ui/badge';
</script>

<section id="about" class="py-24 md:py-32 bg-background">
	<div class="container px-4 md:px-6">
		<div class="space-y-12">
			<!-- About Section -->
			<div class="text-center space-y-4 max-w-3xl mx-auto">
				<h2 class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl">About Me</h2>
				<p class="text-lg text-muted-foreground">
					Passionate fullstack developer with extensive experience in building modern, scalable web applications.
					I specialize in creating intuitive user interfaces while maintaining robust backend systems. 
					My expertise lies in translating complex requirements into elegant, user-friendly solutions.
				</p>
			</div>

			<!-- Skills Section -->
			<div class="grid gap-6 md:grid-cols-2">
				<!-- Preferred Technologies -->
				<Card class="border-primary/50">
					<CardHeader>
						<CardTitle class="text-2xl">Preferred Technologies</CardTitle>
						<CardDescription>My go-to stack for building exceptional applications</CardDescription>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h4 class="text-sm font-semibold mb-3 text-muted-foreground">Frontend</h4>
							<div class="flex flex-wrap gap-2">
								<Badge variant="default">React</Badge>
								<Badge variant="default">Tailwind CSS</Badge>
								<Badge variant="default">TypeScript</Badge>
							</div>
						</div>
						<div>
							<h4 class="text-sm font-semibold mb-3 text-muted-foreground">Backend</h4>
							<div class="flex flex-wrap gap-2">
								<Badge variant="default">Node.js</Badge>
								<Badge variant="default">Express.js</Badge>
								<Badge variant="default">Koa.js</Badge>
							</div>
						</div>
						<div>
							<h4 class="text-sm font-semibold mb-3 text-muted-foreground">Database & Caching</h4>
							<div class="flex flex-wrap gap-2">
								<Badge variant="default">PostgreSQL</Badge>
								<Badge variant="default">Redis</Badge>
							</div>
						</div>
					</CardContent>
				</Card>

				<!-- Alternative Technologies -->
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Alternative Technologies</CardTitle>
						<CardDescription>Additional tools and frameworks I work with</CardDescription>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h4 class="text-sm font-semibold mb-3 text-muted-foreground">Frontend</h4>
							<div class="flex flex-wrap gap-2">
								<Badge variant="secondary">Svelte</Badge>
								<Badge variant="secondary">SvelteKit</Badge>
								<Badge variant="secondary">Next.js</Badge>
							</div>
						</div>
						<div>
							<h4 class="text-sm font-semibold mb-3 text-muted-foreground">Backend</h4>
							<div class="flex flex-wrap gap-2">
								<Badge variant="secondary">Python</Badge>
								<Badge variant="secondary">Django</Badge>
							</div>
						</div>
						<div>
							<h4 class="text-sm font-semibold mb-3 text-muted-foreground">Tools & Others</h4>
							<div class="flex flex-wrap gap-2">
								<Badge variant="secondary">Git</Badge>
								<Badge variant="secondary">Docker</Badge>
								<Badge variant="secondary">REST APIs</Badge>
								<Badge variant="secondary">GraphQL</Badge>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</div>
	</div>
</section>
