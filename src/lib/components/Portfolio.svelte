<script lang="ts">
  import { Badge } from "$lib/components/ui/badge";
  import {
    Card,
    CardContent,
    CardDescription,
    CardHeader,
    CardTitle,
  } from "$lib/components/ui/card";

  let expandedImage: string | null = null;

  function toggleImage(imageSrc: string) {
    expandedImage = expandedImage === imageSrc ? null : imageSrc;
  }
</script>

<section id="portfolio" class="py-24 md:py-32 bg-secondary/10">
  <div class="container px-4 md:px-6">
    <div class="space-y-12">
      <div class="text-center space-y-4 max-w-3xl mx-auto">
        <h2 class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl">
          Featured Work
        </h2>
        <p class="text-lg text-muted-foreground">
          Crafting digital experiences that make a difference. Here's a glimpse
          of what I'm building, with more innovative solutions on the horizon.
        </p>
      </div>

      <div class="max-w-7xl mx-auto">
        <!-- Church Management System Project -->
        <Card
          class="flex flex-col h-full transition-all hover:shadow-xl hover:-translate-y-2 border-primary/20"
        >
          <CardHeader>
            <div class="flex items-start justify-between gap-4 flex-wrap">
              <div class="space-y-3 flex-1">
                <div class="flex items-center gap-3 flex-wrap">
                  <CardTitle class="text-3xl"
                    >Church Management System</CardTitle
                  >
                  <Badge
                    variant="default"
                    class="bg-green-500/10 text-green-600 border-green-500/20 hover:bg-green-500/20"
                  >
                    Ongoing Project
                  </Badge>
                </div>
                <CardDescription class="text-base">
                  A comprehensive web solution empowering churches to connect
                  with their community and streamline administrative workflows
                </CardDescription>
              </div>
            </div>
          </CardHeader>
          <CardContent class="flex-1 space-y-6">
            <!-- Project Screenshots -->
            <div class="grid grid-cols-3 gap-4">
              <button
                type="button"
                class="relative aspect-video rounded-lg overflow-hidden border border-border hover:scale-105 transition-transform cursor-pointer"
                on:click={() => toggleImage("/web-church-1.png")}
              >
                <img
                  src="/web-church-1.png"
                  alt="Church Management System - Dashboard"
                  class="w-full h-full object-cover"
                />
              </button>
              <button
                type="button"
                class="relative aspect-video rounded-lg overflow-hidden border border-border hover:scale-105 transition-transform cursor-pointer"
                on:click={() => toggleImage("/web-church-2.png")}
              >
                <img
                  src="/web-church-2.png"
                  alt="Church Management System - Users"
                  class="w-full h-full object-cover"
                />
              </button>
              <button
                type="button"
                class="relative aspect-video rounded-lg overflow-hidden border border-border hover:scale-105 transition-transform cursor-pointer"
                on:click={() => toggleImage("/web-church-3.png")}
              >
                <img
                  src="/web-church-3.png"
                  alt="Church Management System - Members"
                  class="w-full h-full object-cover"
                />
              </button>
            </div>

            <div class="grid md:grid-cols-2 gap-6">
              <div class="space-y-3">
                <h4 class="text-sm font-bold text-primary">
                  Public-Facing Features
                </h4>
                <ul class="space-y-2 text-sm text-muted-foreground">
                  <li class="flex items-start">
                    <span class="mr-2 text-primary">✓</span>
                    <span
                      >Modern and responsive landing page optimized for visitor
                      engagement</span
                    >
                  </li>
                  <li class="flex items-start">
                    <span class="mr-2 text-primary">✓</span>
                    <span>Dynamic announcements and ministry highlights</span>
                  </li>
                  <li class="flex items-start">
                    <span class="mr-2 text-primary">✓</span>
                    <span>Seamless contact and inquiry submission system</span>
                  </li>
                </ul>
              </div>
              <div class="space-y-3">
                <h4 class="text-sm font-bold text-primary">Admin Dashboard</h4>
                <ul class="space-y-2 text-sm text-muted-foreground">
                  <li class="flex items-start">
                    <span class="mr-2 text-primary">✓</span>
                    <span
                      >Comprehensive member database with detailed profiles</span
                    >
                  </li>
                  <li class="flex items-start">
                    <span class="mr-2 text-primary">✓</span>
                    <span
                      >Role-based access control for administrative team</span
                    >
                  </li>
                  <li class="flex items-start">
                    <span class="mr-2 text-primary">✓</span>
                    <span
                      >Activity tracking and audit logs for transparency</span
                    >
                  </li>
                </ul>
              </div>
            </div>

            <div class="space-y-3 pt-4 border-t">
              <h4 class="text-sm font-bold">Technology Stack</h4>
              <div class="flex flex-wrap gap-2">
                <Badge variant="secondary">SvelteKit</Badge>
                <Badge variant="secondary">TypeScript</Badge>
                <Badge variant="secondary">PostgreSQL</Badge>
                <Badge variant="secondary">Tailwind CSS</Badge>
                <Badge variant="secondary">shadcn/ui</Badge>
                <Badge variant="secondary">Auth Js</Badge>
                <Badge variant="secondary">Resend</Badge>
              </div>
            </div>
          </CardContent>
        </Card>
      </div>
    </div>
  </div>
</section>

<!-- Image Expansion Modal -->
{#if expandedImage}
  <div
    class="fixed inset-0 bg-black/80 z-50 flex items-center justify-center p-4"
    on:click={() => (expandedImage = null)}
    on:keydown={(e) => e.key === "Escape" && (expandedImage = null)}
    role="button"
    tabindex="0"
  >
    <div class="relative max-w-6xl w-full">
      <button
        type="button"
        class="absolute top-4 right-4 text-white bg-black/50 rounded-full p-2 hover:bg-black/70 transition-colors z-10"
        on:click={() => (expandedImage = null)}
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path d="M18 6 6 18"></path>
          <path d="m6 6 12 12"></path>
        </svg>
      </button>
      <img
        src={expandedImage}
        alt="Expanded view"
        class="w-full h-auto rounded-lg"
        on:click={(e) => e.stopPropagation()}
      />
    </div>
  </div>
{/if}
