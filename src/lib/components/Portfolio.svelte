<script lang="ts">
	import { Card, CardContent, CardDescription, CardHeader, CardTitle } from '$lib/components/ui/card';
	import { Badge } from '$lib/components/ui/badge';
	import { Button } from '$lib/components/ui/button';
	import { ExternalLink } from 'lucide-svelte';
</script>

<section id="portfolio" class="py-24 md:py-32 bg-secondary/10">
	<div class="container px-4 md:px-6">
		<div class="space-y-12">
			<div class="text-center space-y-4">
				<h2 class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl">Portfolio</h2>
				<p class="text-lg text-muted-foreground max-w-2xl mx-auto">
					A selection of projects showcasing my expertise in fullstack development
				</p>
			</div>

			<div class="grid gap-8 md:grid-cols-2">
				<!-- Expense Tracker Project -->
				<Card class="flex flex-col h-full transition-all hover:shadow-lg hover:-translate-y-1">
					<CardHeader>
						<div class="flex items-start justify-between">
							<div class="space-y-2 flex-1">
								<CardTitle class="text-2xl">Expense Tracker</CardTitle>
								<CardDescription>Personal application for expense management with intelligent analysis</CardDescription>
							</div>
						</div>
					</CardHeader>
					<CardContent class="flex-1 space-y-4">
						<div class="space-y-3">
							<h4 class="text-sm font-semibold">Key Features</h4>
							<ul class="space-y-2 text-sm text-muted-foreground">
								<li class="flex items-start">
									<span class="mr-2">•</span>
									<span>Intelligent analysis of needs vs. wants spending patterns</span>
								</li>
								<li class="flex items-start">
									<span class="mr-2">•</span>
									<span>Advanced categorization system for expense tracking</span>
								</li>
								<li class="flex items-start">
									<span class="mr-2">•</span>
									<span>Money source tracking with detailed insights</span>
								</li>
								<li class="flex items-start">
									<span class="mr-2">•</span>
									<span>Visual reports and analytics dashboard</span>
								</li>
							</ul>
						</div>
						<div class="space-y-2">
							<h4 class="text-sm font-semibold">Technologies</h4>
							<div class="flex flex-wrap gap-2">
								<Badge>React</Badge>
								<Badge>Node.js</Badge>
								<Badge>PostgreSQL</Badge>
								<Badge>Tailwind CSS</Badge>
								<Badge>Express.js</Badge>
							</div>
						</div>
					</CardContent>
				</Card>

				<!-- Church Website Project -->
				<Card class="flex flex-col h-full transition-all hover:shadow-lg hover:-translate-y-1">
					<CardHeader>
						<div class="flex items-start justify-between">
							<div class="space-y-2 flex-1">
								<CardTitle class="text-2xl">Church Website</CardTitle>
								<CardDescription>Complete web solution for church management and community engagement</CardDescription>
							</div>
						</div>
					</CardHeader>
					<CardContent class="flex-1 space-y-4">
						<div class="space-y-3">
							<h4 class="text-sm font-semibold">Key Features</h4>
							<ul class="space-y-2 text-sm text-muted-foreground">
								<li class="flex items-start">
									<span class="mr-2">•</span>
									<span>Professional public landing page for visitor information</span>
								</li>
								<li class="flex items-start">
									<span class="mr-2">•</span>
									<span>Comprehensive admin dashboard for church management</span>
								</li>
								<li class="flex items-start">
									<span class="mr-2">•</span>
									<span>Member management system with role-based access</span>
								</li>
								<li class="flex items-start">
									<span class="mr-2">•</span>
									<span>Event scheduling and announcement features</span>
								</li>
							</ul>
						</div>
						<div class="space-y-2">
							<h4 class="text-sm font-semibold">Technologies</h4>
							<div class="flex flex-wrap gap-2">
								<Badge>React</Badge>
								<Badge>Next.js</Badge>
								<Badge>Node.js</Badge>
								<Badge>PostgreSQL</Badge>
								<Badge>Tailwind CSS</Badge>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</div>
	</div>
</section>
