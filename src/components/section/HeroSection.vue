<script setup lang="ts">

import {Avatar, AvatarFallback, AvatarImage} from "@/components/ui/avatar";
import {Separator} from "@/components/ui/separator";
import {Button} from "@/components/ui/button";
import {Linkedin, Github, Instagram} from 'lucide-vue-next';
import TypeWriter from "@/components/TypeWriter.vue";
import {Tooltip, TooltipContent, TooltipProvider, TooltipTrigger} from "@/components/ui/tooltip";

const greetings = ["Hello", "Moin", "Bonjour", "Hola", "Hej", "Konnichiwa", "nǐ hǎo", "Grüezi", "Merhaba"]

function openLink(link: string) {
  window.open(link)
}

</script>

<template>
  <section class="hero w-full h-screen">
    <div class="flex flex-row">
      <div class="flex flex-[30%] w-full h-screen place-content-center items-center">
        <Avatar class="h-80 w-80">
          <AvatarImage src="https://avatars.githubusercontent.com/u/88259038" alt="Avatar"/>
          <AvatarFallback>LS</AvatarFallback>
        </Avatar>
      </div>
      <div class="flex-[70%] w-full h-screen place-content-center items-center">
        <!-- About me text -->
        <TypeWriter class="text-2xl text-primary" :words="greetings"/>
        <h1 class="text-4xl font-bold">I'm Luca,</h1>
        <p class="text-2xl mt-2">a software developer with a keen interest in open source projects. <br>
          I also love nature and do a lot of sport to balance out my office work.</p>

        <!-- Quote -->
        <div class="border-l-2 border-l-primary mt-4">
          <p class="text-xl text-secondary ml-2">"The only way to do great work is to love what you do." - Steve
            Jobs</p>
        </div>


        <!-- Social media buttons -->
        <div class="flex flex-row gap-1 mt-8">
          <!-- Contact me button -->
          <TooltipProvider>
            <Tooltip>
              <TooltipTrigger>
                <Button @click="openLink('mailto:me@lucaschumacher.com')">
                  Contact me
                </Button>
              </TooltipTrigger>
              <TooltipContent side="bottom" class="bg-accent">
                <p>Write me an email</p>
              </TooltipContent>
            </Tooltip>
          </TooltipProvider>

          <Separator orientation="vertical"/>

          <!-- LinkedIn -->
          <TooltipProvider>
            <Tooltip>
              <TooltipTrigger>
                <Button variant="link" @click="openLink('https://www.linkedin.com/in/lucaschumacher/')">
                  <Linkedin/>
                </Button>
              </TooltipTrigger>
              <TooltipContent side="bottom" class="bg-accent">
                <p>Take a look at my career</p>
              </TooltipContent>
            </Tooltip>
          </TooltipProvider>

          <!-- GitHub -->
          <TooltipProvider>
            <Tooltip>
              <TooltipTrigger>
                <Button variant="link" @click="openLink('https://github.com/LuftigerLuca')">
                  <Github/>
                </Button>
              </TooltipTrigger>
              <TooltipContent side="bottom" class="bg-accent">
                <p>Take a look at my opensource projects :)</p>
              </TooltipContent>
            </Tooltip>
          </TooltipProvider>


          <!-- Instagram -->
          <TooltipProvider>
            <Tooltip>
              <TooltipTrigger>
                <Button variant="link" @click="openLink('https://www.instagram.com/luca.a.s/')">
                  <Instagram/>
                </Button>
              </TooltipTrigger>
              <TooltipContent side="bottom" class="bg-accent">
                <p>Follow me on Instagram</p>
              </TooltipContent>
            </Tooltip>
          </TooltipProvider>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>