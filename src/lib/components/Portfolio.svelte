<script lang="ts">
  import { Badge } from "$lib/components/ui/badge";
  import {
    Card,
    CardContent,
    CardDescription,
    CardHeader,
    CardTitle,
  } from "$lib/components/ui/card";
  import { ChevronLeft, ChevronRight } from "lucide-svelte";

  let expandedImage = $state<string | null>(null);
  let currentIndex = $state(0);
  const totalSlides = 3;

  function toggleImage(imageSrc: string) {
    expandedImage = expandedImage === imageSrc ? null : imageSrc;
  }

  function nextSlide() {
    currentIndex = (currentIndex + 1) % totalSlides;
  }

  function prevSlide() {
    currentIndex = (currentIndex - 1 + totalSlides) % totalSlides;
  }

  function goToSlide(index: number) {
    currentIndex = index;
  }

  let touchStartX = 0;
  let touchEndX = 0;

  function handleTouchStart(e: TouchEvent) {
    touchStartX = e.changedTouches[0].screenX;
  }

  function handleTouchEnd(e: TouchEvent) {
    touchEndX = e.changedTouches[0].screenX;
    const threshold = 50;
    if (touchEndX < touchStartX - threshold) {
      nextSlide();
    } else if (touchEndX > touchStartX + threshold) {
      prevSlide();
    }
  }
</script>

<svelte:window
  onkeydown={(e) => {
    if (e.key === "Escape") expandedImage = null;
    if (e.key === "ArrowLeft" && !expandedImage) prevSlide();
    if (e.key === "ArrowRight" && !expandedImage) nextSlide();
  }}
/>

<section id="portfolio" class="py-24 md:py-32 bg-secondary/10">
  <div class="container px-4 md:px-6">
    <div class="space-y-10">
      <div class="text-center space-y-4 max-w-3xl mx-auto">
        <h2 class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl">
          Featured Work
        </h2>
        <p class="text-lg text-muted-foreground">
          Crafting digital experiences that make a difference. Here's a glimpse
          of what I've built and contributed to, with more innovative solutions
          on the horizon.
        </p>
      </div>

      <div class="max-w-7xl mx-auto space-y-6">
        <!-- Carousel Controls Bar -->
        <div class="flex items-center justify-between gap-4 flex-wrap">
          <div
            class="inline-flex items-center p-1 bg-muted/60 backdrop-blur rounded-full border border-border/60 shadow-inner"
          >
            <button
              type="button"
              class="px-4 py-1.5 text-xs sm:text-sm font-medium rounded-full transition-all cursor-pointer {currentIndex ===
              0
                ? 'bg-background text-foreground shadow-sm'
                : 'text-muted-foreground hover:text-foreground'}"
              onclick={() => goToSlide(0)}
            >
              Church Management
            </button>
            <button
              type="button"
              class="px-4 py-1.5 text-xs sm:text-sm font-medium rounded-full transition-all cursor-pointer {currentIndex ===
              1
                ? 'bg-background text-foreground shadow-sm'
                : 'text-muted-foreground hover:text-foreground'}"
              onclick={() => goToSlide(1)}
            >
              MataHati
            </button>
            <button
              type="button"
              class="px-4 py-1.5 text-xs sm:text-sm font-medium rounded-full transition-all cursor-pointer {currentIndex ===
              2
                ? 'bg-background text-foreground shadow-sm'
                : 'text-muted-foreground hover:text-foreground'}"
              onclick={() => goToSlide(2)}
            >
              Telegram Bot
            </button>
          </div>

          <div class="flex items-center gap-2">
            <span class="text-xs text-muted-foreground mr-1 hidden sm:inline">
              {currentIndex + 1} of {totalSlides}
            </span>
            <button
              type="button"
              class="p-2 rounded-full border border-border bg-background/80 hover:bg-accent text-foreground transition-all cursor-pointer shadow-sm hover:scale-105 active:scale-95"
              onclick={prevSlide}
              aria-label="Previous project"
            >
              <ChevronLeft class="w-5 h-5" />
            </button>
            <button
              type="button"
              class="p-2 rounded-full border border-border bg-background/80 hover:bg-accent text-foreground transition-all cursor-pointer shadow-sm hover:scale-105 active:scale-95"
              onclick={nextSlide}
              aria-label="Next project"
            >
              <ChevronRight class="w-5 h-5" />
            </button>
          </div>
        </div>

        <!-- Carousel Container with Sliding Track -->
        <div
          class="relative overflow-hidden w-full rounded-2xl"
          ontouchstart={handleTouchStart}
          ontouchend={handleTouchEnd}
          role="region"
          aria-roledescription="carousel"
          aria-label="Featured projects"
        >
          <div
            class="flex transition-transform duration-500 ease-out"
            style="transform: translateX(-{currentIndex * 100}%);"
          >
            <!-- Slide 1: Church Management System Project -->
            <div class="w-full flex-shrink-0">
              <Card
                class="flex flex-col h-full transition-all hover:shadow-xl border-primary/20"
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
                          Done
                        </Badge>
                      </div>
                      <CardDescription class="text-base">
                        A comprehensive web solution empowering churches to
                        connect with their community and streamline
                        administrative workflows
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
                      onclick={() => toggleImage("/web-church-1.png")}
                      aria-label="View Church Management System Dashboard screenshot"
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
                      onclick={() => toggleImage("/web-church-2.png")}
                      aria-label="View Church Management System Users screenshot"
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
                      onclick={() => toggleImage("/web-church-3.png")}
                      aria-label="View Church Management System Members screenshot"
                    >
                      <img
                        src="/web-church-3.png"
                        alt="Church Management System - Members"
                        class="w-full h-full object-cover"
                      />
                    </button>
                  </div>

                  <div class="space-y-3">
                    <h4 class="text-sm font-bold text-primary">
                      Admin Dashboard
                    </h4>
                    <ul
                      class="space-y-2 text-sm text-muted-foreground sm:grid sm:grid-cols-3 sm:space-y-0 sm:gap-4"
                    >
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

            <!-- Slide 2: MataHati Project -->
            <div class="w-full flex-shrink-0">
              <Card
                class="flex flex-col h-full transition-all hover:shadow-xl border-primary/20"
              >
                <CardHeader>
                  <div class="flex items-start justify-between gap-4 flex-wrap">
                    <div class="space-y-3 flex-1">
                      <div class="flex items-center gap-3 flex-wrap">
                        <CardTitle class="text-3xl">MataHati</CardTitle>
                        <Badge
                          variant="outline"
                          class="border-primary/30 text-primary bg-primary/5 font-medium"
                        >
                          Integration Collaboration with Tenang.AI
                        </Badge>
                        <Badge
                          variant="default"
                          class="bg-green-500/10 text-green-600 border-green-500/20 hover:bg-green-500/20"
                        >
                          Done
                        </Badge>
                      </div>
                      <CardDescription class="text-base leading-relaxed">
                        A local mental health support platform by <strong
                          class="text-foreground font-semibold"
                          >Tenang.AI</strong
                        > for Dinas Kesehatan Kabupaten Sleman. I collaborated with
                        my friend, the CEO of Tenang.AI, to help integrate their
                        LLM-powered AI co-psychologist companion and public healthcare
                        referral workflows into the platform.
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
                      onclick={() => toggleImage("/matahati-1.png")}
                      aria-label="View MataHati Landing Page screenshot"
                    >
                      <img
                        src="/matahati-1.png"
                        alt="MataHati - Landing Page & AI Companion Introduction"
                        class="w-full h-full object-cover"
                      />
                    </button>
                    <button
                      type="button"
                      class="relative aspect-video rounded-lg overflow-hidden border border-border hover:scale-105 transition-transform cursor-pointer"
                      onclick={() => toggleImage("/matahati-2.png")}
                      aria-label="View MataHati Authentication screenshot"
                    >
                      <img
                        src="/matahati-2.png"
                        alt="MataHati - Secure Authentication"
                        class="w-full h-full object-cover"
                      />
                    </button>
                    <button
                      type="button"
                      class="relative aspect-video rounded-lg overflow-hidden border border-border hover:scale-105 transition-transform cursor-pointer"
                      onclick={() => toggleImage("/matahati-3.png")}
                      aria-label="View MataHati Patient Dashboard screenshot"
                    >
                      <img
                        src="/matahati-3.png"
                        alt="MataHati - Patient Dashboard & Services"
                        class="w-full h-full object-cover"
                      />
                    </button>
                  </div>

                  <div class="space-y-3">
                    <h4 class="text-sm font-bold text-primary">
                      Integration & Key Highlights
                    </h4>
                    <ul
                      class="space-y-2 text-sm text-muted-foreground sm:grid sm:grid-cols-3 sm:space-y-0 sm:gap-4"
                    >
                      <li class="flex items-start">
                        <span class="mr-2 text-primary">✓</span>
                        <span
                          >Assisted Tenang.AI in integrating LLM conversational
                          capabilities as an AI mental wellbeing companion</span
                        >
                      </li>
                      <li class="flex items-start">
                        <span class="mr-2 text-primary">✓</span>
                        <span
                          >Integrated direct referral bridge connecting users to
                          psychologists and Sleman Health Department services</span
                        >
                      </li>
                      <li class="flex items-start">
                        <span class="mr-2 text-primary">✓</span>
                        <span
                          >Implemented secure patient portal flows with session
                          tracking and crisis support pathways</span
                        >
                      </li>
                    </ul>
                  </div>

                  <div class="space-y-3 pt-4 border-t">
                    <h4 class="text-sm font-bold">Technology Stack</h4>
                    <div class="flex flex-wrap gap-2">
                      <Badge variant="secondary">LLM</Badge>
                      <Badge variant="secondary">AI Co-Psychologist</Badge>
                      <Badge variant="secondary">NextJs</Badge>
                      <Badge variant="secondary">TypeScript</Badge>
                      <Badge variant="secondary">Tailwind CSS</Badge>
                      <Badge variant="secondary">PostgreSQL</Badge>
                    </div>
                  </div>
                </CardContent>
              </Card>
            </div>

            <!-- Slide 3: Telegram Bot Project -->
            <div class="w-full flex-shrink-0">
              <Card
                class="flex flex-col h-full transition-all hover:shadow-xl border-primary/20"
              >
                <CardHeader>
                  <div class="flex items-start justify-between gap-4 flex-wrap">
                    <div class="space-y-3 flex-1">
                      <div class="flex items-center gap-3 flex-wrap">
                        <CardTitle class="text-3xl"
                          >Telegram Bot for Group Management</CardTitle
                        >
                        <Badge
                          variant="default"
                          class="bg-amber-500/10 text-amber-600 dark:text-amber-400 border-amber-500/20 hover:bg-amber-500/20 gap-1.5"
                        >
                          <span
                            class="w-1.5 h-1.5 rounded-full bg-amber-500 animate-pulse"
                          ></span>
                          Under Development
                        </Badge>
                      </div>
                      <CardDescription class="text-base leading-relaxed">
                        A robust, modular Telegram bot designed for dedicated
                        single-group management with upcoming multi-tenant
                        capabilities, anti-spam protection, automated member
                        onboarding, and granular moderation.
                      </CardDescription>
                    </div>
                  </div>
                </CardHeader>
                <CardContent class="flex-1 space-y-6">
                  <!-- Project Preview / Under Development Banner -->
                  <div class="grid grid-cols-3 gap-4">
                    <button
                      type="button"
                      class="relative aspect-video rounded-lg overflow-hidden border border-border hover:scale-105 transition-transform cursor-pointer shadow-sm group block bg-background/50"
                      onclick={() => toggleImage("/telegram-bot-preview.jpg")}
                      aria-label="View Telegram Bot project preview and development status"
                    >
                      <img
                        src="/telegram-bot-preview.jpg"
                        alt="Telegram Bot for Group Management - Under Development / Coming Soon"
                        class="w-full h-full object-cover"
                      />
                    </button>
                  </div>

                  <div class="space-y-3">
                    <h4 class="text-sm font-bold text-primary">
                      Core Features & Architecture
                    </h4>
                    <ul
                      class="space-y-2 text-sm text-muted-foreground sm:grid sm:grid-cols-3 sm:space-y-0 sm:gap-4"
                    >
                      <li class="flex items-start">
                        <span class="mr-2 text-primary">✓</span>
                        <span
                          >Automated spam filtering, anti-flood rate limits, and
                          verification CAPTCHA for incoming members</span
                        >
                      </li>
                      <li class="flex items-start">
                        <span class="mr-2 text-primary">✓</span>
                        <span
                          >Granular moderation commands, warning counters, and
                          automated temporary bans/mutes</span
                        >
                      </li>
                      <li class="flex items-start">
                        <span class="mr-2 text-primary">✓</span>
                        <span
                          >Modular plugin architecture with grammY middleware
                          for scalable command handling</span
                        >
                      </li>
                    </ul>
                  </div>

                  <div class="space-y-3 pt-4 border-t">
                    <h4 class="text-sm font-bold">Technology Stack</h4>
                    <div class="flex flex-wrap gap-2">
                      <Badge variant="secondary">TypeScript</Badge>
                      <Badge variant="secondary">grammY</Badge>
                      <Badge variant="secondary">Telegram Bot API</Badge>
                      <Badge variant="secondary">Node.js</Badge>
                    </div>
                  </div>
                </CardContent>
              </Card>
            </div>
          </div>
        </div>

        <!-- Slide Indicator Dots -->
        <div class="flex justify-center items-center gap-2 pt-2">
          {#each [0, 1, 2] as index (index)}
            <button
              type="button"
              class="h-2 rounded-full transition-all cursor-pointer {currentIndex ===
              index
                ? 'w-8 bg-primary'
                : 'w-2 bg-muted-foreground/30 hover:bg-muted-foreground/60'}"
              onclick={() => goToSlide(index)}
              aria-label="Go to project {index + 1}"
            ></button>
          {/each}
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Image Expansion Modal -->
{#if expandedImage}
  <div
    class="fixed inset-0 bg-black/80 z-50 flex items-center justify-center p-4 cursor-pointer"
    onclick={(e) => {
      if (e.target === e.currentTarget) expandedImage = null;
    }}
    onkeydown={(e) => {
      if (e.key === "Escape") expandedImage = null;
    }}
    role="button"
    tabindex="0"
    aria-label="Close expanded view overlay"
  >
    <div class="relative max-w-6xl w-full cursor-default">
      <button
        type="button"
        class="absolute top-4 right-4 text-white bg-black/50 rounded-full p-2 hover:bg-black/70 transition-colors z-10"
        onclick={() => (expandedImage = null)}
        aria-label="Close image modal"
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
      />
    </div>
  </div>
{/if}
