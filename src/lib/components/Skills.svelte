<script lang="ts">
  import { Card, CardContent } from "$lib/components/ui/card";

  const strongExpertise = [
    {
      name: "React",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg",
      color: "bg-cyan-500/10 border-cyan-500/20",
    },
    {
      name: "TypeScript",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg",
      color: "bg-blue-500/10 border-blue-500/20",
    },
    {
      name: "Tailwind CSS",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original.svg",
      color: "bg-sky-500/10 border-sky-500/20",
    },
    {
      name: "Node.js",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg",
      color: "bg-green-500/10 border-green-500/20",
    },
    {
      name: "PostgreSQL",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg",
      color: "bg-blue-600/10 border-blue-600/20",
    },
    {
      name: "Redis",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redis/redis-original.svg",
      color: "bg-red-500/10 border-red-500/20",
    },
  ];

  const otherSkills = [
    {
      name: "SvelteKit",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/svelte/svelte-original.svg",
      color: "bg-orange-600/10 border-orange-600/20",
    },
    {
      name: "Next.js",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg",
      color: "bg-gray-500/10 border-gray-500/20",
    },
    {
      name: "Python",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg",
      color: "bg-yellow-500/10 border-yellow-500/20",
    },
    {
      name: "Django",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg",
      color: "bg-green-600/10 border-green-600/20",
    },
    {
      name: "Express.js",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg",
      color: "bg-gray-600/10 border-gray-600/20",
    },
    {
      name: "Koa.js",
      icon: "https://www.vectorlogo.zone/logos/koajs/koajs-ar21.svg",
      color: "bg-teal-500/10 border-teal-500/20",
    },
    {
      name: "Docker",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg",
      color: "bg-blue-400/10 border-blue-400/20",
    },
    {
      name: "Git",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg",
      color: "bg-orange-700/10 border-orange-700/20",
    },
    {
      name: "Java",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg",
      color: "bg-red-600/10 border-red-600/20",
    },
    {
      name: "Spring Boot",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg",
      color: "bg-green-500/10 border-green-500/20",
    },
    {
      name: "Vue.js",
      icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg",
      color: "bg-emerald-500/10 border-emerald-500/20",
    },
  ];
</script>

<section id="about" class="py-24 md:py-32 bg-background">
  <div class="container px-4 md:px-6">
    <div class="space-y-12">
      <!-- About Section -->
      <div class="text-center space-y-4 max-w-3xl mx-auto">
        <h2 class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl">
          About Me
        </h2>
        <p class="text-lg text-muted-foreground">
          Senior Software Engineer with 7+ years of experience in software
          development and team leadership, successfully led AccelByte web team
          for 2K Games client from the ground up. I specialize in creating
          intuitive user interfaces while maintaining robust backend systems. My
          expertise lies in translating complex requirements into elegant,
          user-friendly solutions.
        </p>
      </div>

      <!-- Skills Section -->
      <div class="space-y-8">
        <h3 class="text-2xl font-bold text-center">Technologies & Tools</h3>

        <!-- Strong Expertise - Scroll Right to Left -->
        <div class="relative overflow-hidden">
          <div class="scroll-container-rtl flex gap-4">
            {#each [...strongExpertise, ...strongExpertise] as tech}
              <Card
                class="border-2 {tech.color} transition-all hover:scale-105 hover:shadow-lg flex-shrink-0 w-[180px]"
              >
                <CardContent
                  class="p-6 flex flex-col items-center justify-center space-y-3"
                >
                  <img
                    src={tech.icon}
                    alt={tech.name}
                    class="w-12 h-12 object-contain"
                  />
                  <p class="text-sm font-semibold text-center">{tech.name}</p>
                </CardContent>
              </Card>
            {/each}
          </div>
        </div>

        <!-- Other Skills - Scroll Left to Right -->
        <div class="relative overflow-hidden">
          <div class="scroll-container-ltr flex gap-4">
            {#each [...otherSkills, ...otherSkills] as tech}
              <Card
                class="border {tech.color} transition-all hover:scale-105 hover:shadow-md flex-shrink-0 w-[130px]"
              >
                <CardContent
                  class="p-4 flex flex-col items-center justify-center space-y-2"
                >
                  <img
                    src={tech.icon}
                    alt={tech.name}
                    class="w-10 h-10 object-contain {[
                      'Express.js',
                      'Koa.js',
                    ].includes(tech.name)
                      ? 'dark:invert'
                      : ''}"
                  />
                  <p class="text-xs font-medium text-center">{tech.name}</p>
                </CardContent>
              </Card>
            {/each}
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  @keyframes scroll-rtl {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }

  @keyframes scroll-ltr {
    0% {
      transform: translateX(-50%);
    }
    100% {
      transform: translateX(0);
    }
  }

  .scroll-container-rtl {
    animation: scroll-rtl 20s linear infinite;
  }

  .scroll-container-rtl:hover {
    animation-play-state: paused;
  }

  .scroll-container-ltr {
    animation: scroll-ltr 25s linear infinite;
  }

  .scroll-container-ltr:hover {
    animation-play-state: paused;
  }
</style>
