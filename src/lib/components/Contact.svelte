<script lang="ts">
  import { Button } from "$lib/components/ui/button";
  import {
    Card,
    CardContent,
    CardDescription,
    CardHeader,
    CardTitle,
  } from "$lib/components/ui/card";
  import { Github, Linkedin, Mail } from "lucide-svelte";
</script>

<section id="contact" class="py-24 md:py-32 bg-background">
  <div class="container px-4 md:px-6">
    <div class="space-y-12">
      <div class="text-center space-y-4">
        <h2 class="text-3xl font-bold tracking-tighter sm:text-4xl md:text-5xl">
          Get in Touch
        </h2>
        <p class="text-lg text-muted-foreground max-w-2xl mx-auto">
          Interested in working together? Feel free to reach out through any of
          these channels.
        </p>
      </div>

      <div class="max-w-2xl mx-auto">
        <Card>
          <CardHeader>
            <CardTitle>Contact Information</CardTitle>
            <CardDescription>Connect with me on these platforms</CardDescription
            >
          </CardHeader>
          <CardContent class="space-y-4">
            <!-- GitHub -->
            <a
              href="https://github.com/isandreas"
              target="_blank"
              rel="noopener noreferrer"
              class="block"
            >
              <Button
                variant="outline"
                class="w-full justify-start h-auto py-4 transition-all hover:bg-accent"
              >
                <div class="flex items-center gap-4 w-full">
                  <div class="p-2 bg-primary/10 rounded-lg">
                    <Github class="h-6 w-6 text-primary" />
                  </div>
                  <div class="flex-1 text-left">
                    <div class="font-semibold">GitHub</div>
                    <div class="text-sm text-muted-foreground">@isandreas</div>
                  </div>
                  <svg
                    class="h-5 w-5 text-muted-foreground"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M9 5l7 7-7 7"
                    ></path>
                  </svg>
                </div>
              </Button>
            </a>

            <!-- LinkedIn -->
            <a
              href="https://linkedin.com/in/andreas-isnawan"
              target="_blank"
              rel="noopener noreferrer"
              class="block"
            >
              <Button
                variant="outline"
                class="w-full justify-start h-auto py-4 transition-all hover:bg-accent"
              >
                <div class="flex items-center gap-4 w-full">
                  <div class="p-2 bg-primary/10 rounded-lg">
                    <Linkedin class="h-6 w-6 text-primary" />
                  </div>
                  <div class="flex-1 text-left">
                    <div class="font-semibold">LinkedIn</div>
                    <div class="text-sm text-muted-foreground">
                      Connect with me professionally
                    </div>
                  </div>
                  <svg
                    class="h-5 w-5 text-muted-foreground"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M9 5l7 7-7 7"
                    ></path>
                  </svg>
                </div>
              </Button>
            </a>

            <!-- Email -->
            <a href="mailto:isandreas.dev@gmail.com" class="block">
              <Button
                variant="outline"
                class="w-full justify-start h-auto py-4 transition-all hover:bg-accent"
              >
                <div class="flex items-center gap-4 w-full">
                  <div class="p-2 bg-primary/10 rounded-lg">
                    <Mail class="h-6 w-6 text-primary" />
                  </div>
                  <div class="flex-1 text-left">
                    <div class="font-semibold">Email</div>
                    <div class="text-sm text-muted-foreground">
                      isandreas.dev@gmail.com
                    </div>
                  </div>
                  <svg
                    class="h-5 w-5 text-muted-foreground"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M9 5l7 7-7 7"
                    ></path>
                  </svg>
                </div>
              </Button>
            </a>
          </CardContent>
        </Card>
      </div>
    </div>
  </div>
</section>

<!-- Footer -->
<footer class="border-t py-8 bg-background">
  <div class="container px-4 md:px-6">
    <div class="flex flex-col md:flex-row justify-between items-center gap-4">
      <p class="text-sm text-muted-foreground text-center md:text-left">
        © {new Date().getFullYear()} Andreas. Built with SvelteKit & shadcn-svelte.
      </p>
      <div class="flex gap-4">
        <a
          href="https://github.com/isandreas"
          target="_blank"
          rel="noopener noreferrer"
          class="text-muted-foreground hover:text-foreground transition-colors"
        >
          <Github class="h-5 w-5" />
          <span class="sr-only">GitHub</span>
        </a>
        <a
          href="https://linkedin.com/in/yourprofile"
          target="_blank"
          rel="noopener noreferrer"
          class="text-muted-foreground hover:text-foreground transition-colors"
        >
          <Linkedin class="h-5 w-5" />
          <span class="sr-only">LinkedIn</span>
        </a>
        <a
          href="mailto:your.email@example.com"
          class="text-muted-foreground hover:text-foreground transition-colors"
        >
          <Mail class="h-5 w-5" />
          <span class="sr-only">Email</span>
        </a>
      </div>
    </div>
  </div>
</footer>
