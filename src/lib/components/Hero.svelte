<script lang="ts">
  import { Button } from "$lib/components/ui/button";
  import { Github, Linkedin, Mail } from "lucide-svelte";
</script>

<section
  class="relative min-h-screen flex items-center justify-center overflow-hidden bg-gradient-to-br from-background via-background to-secondary/30"
>
  <!-- Hexagon background animation -->
  <div class="hexagon-container absolute inset-0 opacity-30">
    <div class="hexagon" style="top: 10%; left: 10%;"></div>
    <div
      class="hexagon"
      style="top: 20%; left: 80%; animation-delay: 1s;"
    ></div>
    <div
      class="hexagon"
      style="top: 60%; left: 15%; animation-delay: 2s;"
    ></div>
    <div
      class="hexagon"
      style="top: 70%; left: 70%; animation-delay: 1.5s;"
    ></div>
    <div
      class="hexagon"
      style="top: 40%; left: 85%; animation-delay: 0.5s;"
    ></div>
    <div
      class="hexagon"
      style="top: 30%; left: 45%; animation-delay: 2.5s;"
    ></div>
  </div>

  <!-- Decorative background elements -->
  <div
    class="absolute inset-0 bg-grid-slate-100 dark:bg-grid-slate-800 [mask-image:linear-gradient(0deg,transparent,black)] opacity-20"
  />
  <div
    class="absolute top-1/4 left-1/4 w-96 h-96 bg-primary/10 rounded-full blur-3xl animate-pulse"
  />
  <div
    class="absolute bottom-1/4 right-1/4 w-96 h-96 bg-secondary/20 rounded-full blur-3xl animate-pulse"
    style="animation-delay: 1s;"
  />

  <div class="container relative px-4 md:px-6 z-10">
    <div class="flex flex-col items-center space-y-10 text-center">
      <div class="space-y-6 max-w-4xl">
        <div
          class="inline-block mb-8 px-4 py-2 rounded-full bg-primary/10 border border-primary/20 animate-in fade-in slide-in-from-bottom-4 duration-700"
        >
          <p class="text-sm font-medium text-primary">Welcome to my page</p>
        </div>

        <h2
          class="text-xl sm:text-2xl md:text-3xl font-medium text-muted-foreground animate-in fade-in slide-in-from-bottom-4 duration-700 delay-100"
        >
          Hello, I'm <span class="text-foreground font-semibold">Andreas</span> 👋
        </h2>

        <h1
          class="hero-title text-5xl font-extrabold tracking-tight sm:text-6xl md:text-7xl lg:text-8xl bg-gradient-to-r from-primary via-primary/80 to-primary/60 bg-clip-text text-transparent animate-in fade-in slide-in-from-bottom-4 duration-700 delay-200 leading-tight transition-all duration-300"
        >
          Senior Software Engineer
        </h1>

        <div
          class="space-y-3 animate-in fade-in slide-in-from-bottom-4 duration-700 delay-300"
        >
          <h2
            class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold text-foreground/90"
          >
            Fullstack Developer
          </h2>
        </div>
      </div>

      <div
        class="flex flex-col sm:flex-row gap-4 pt-4 animate-in fade-in slide-in-from-bottom-4 duration-700 delay-500"
      >
        <Button
          size="lg"
          class="text-base font-semibold shadow-lg hover:shadow-xl transition-all hover:scale-105"
          on:click={() =>
            document
              .getElementById("portfolio")
              ?.scrollIntoView({ behavior: "smooth" })}
        >
          View Portfolio
        </Button>
        <Button
          size="lg"
          variant="outline"
          class="text-base font-semibold hover:scale-105 transition-all"
          on:click={() =>
            document
              .getElementById("contact")
              ?.scrollIntoView({ behavior: "smooth" })}
        >
          Contact Me
        </Button>
      </div>

      <div
        class="flex gap-3 pt-2 animate-in fade-in slide-in-from-bottom-4 duration-700 delay-700"
      >
        <Button
          variant="ghost"
          size="icon"
          class="hover:bg-primary/10 hover:text-primary transition-all hover:scale-110 rounded-full h-12 w-12"
          href="https://github.com/isandreas"
          target="_blank"
          rel="noopener noreferrer"
        >
          <Github class="h-6 w-6" />
          <span class="sr-only">GitHub</span>
        </Button>
        <Button
          variant="ghost"
          size="icon"
          class="hover:bg-primary/10 hover:text-primary transition-all hover:scale-110 rounded-full h-12 w-12"
          href="https://linkedin.com/in/andreas-isnawan"
          target="_blank"
          rel="noopener noreferrer"
        >
          <Linkedin class="h-6 w-6" />
          <span class="sr-only">LinkedIn</span>
        </Button>
        <Button
          variant="ghost"
          size="icon"
          class="hover:bg-primary/10 hover:text-primary transition-all hover:scale-110 rounded-full h-12 w-12"
          href="mailto:isandreas.dev@gmail.com"
        >
          <Mail class="h-6 w-6" />
          <span class="sr-only">Email</span>
        </Button>
      </div>
    </div>
  </div>

  <!-- Scroll indicator -->
  <div
    class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce opacity-60 hover:opacity-100 transition-opacity cursor-pointer"
    role="button"
    tabindex="0"
    on:click={() =>
      document
        .getElementById("portfolio")
        ?.scrollIntoView({ behavior: "smooth" })}
    on:keydown={(e) =>
      e.key === "Enter" &&
      document
        .getElementById("portfolio")
        ?.scrollIntoView({ behavior: "smooth" })}
  >
    <svg
      class="w-6 h-6 text-muted-foreground"
      fill="none"
      stroke="currentColor"
      viewBox="0 0 24 24"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M19 14l-7 7m0 0l-7-7m7 7V3"
      ></path>
    </svg>
  </div>
</section>

<style>
  @keyframes pulse {
    0%,
    100% {
      opacity: 0.4;
    }
    50% {
      opacity: 0.6;
    }
  }

  /* Hexagon animation */
  .hexagon-container {
    pointer-events: none;
  }

  .hexagon {
    position: absolute;
    width: 100px;
    height: 58px;
    background: linear-gradient(
      135deg,
      hsl(var(--primary) / 0.3),
      hsl(var(--primary) / 0.1)
    );
    animation: float 6s ease-in-out infinite;
  }

  .hexagon:before,
  .hexagon:after {
    content: "";
    position: absolute;
    width: 0;
    border-left: 50px solid transparent;
    border-right: 50px solid transparent;
  }

  .hexagon:before {
    bottom: 100%;
    border-bottom: 29px solid;
    border-bottom-color: inherit;
  }

  .hexagon:after {
    top: 100%;
    border-top: 29px solid;
    border-top-color: inherit;
  }

  @keyframes float {
    0%,
    100% {
      transform: translateY(0) rotate(0deg);
    }
    50% {
      transform: translateY(-30px) rotate(5deg);
    }
  }

  /* Hero title hover effect */
  .hero-title {
    position: relative;
    transition: all 0.3s ease;
    display: inline-block;
    width: fit-content;
  }

  .hero-title:hover {
    background: transparent !important;
    -webkit-background-clip: text !important;
    background-clip: text !important;
    -webkit-text-fill-color: white;
    color: white;
  }

  :global(.dark) .hero-title:hover {
    -webkit-text-fill-color: white;
    color: white;
  }

  :global(.light) .hero-title:hover,
  :global(html:not(.dark)) .hero-title:hover {
    -webkit-text-fill-color: black;
    color: black;
  }
</style>
