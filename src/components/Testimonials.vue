<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";

import { Star } from "lucide-vue-next";

interface ReviewProps {
  image: string;
  name: string;
  userName: string;
  comment: string;
  rating: number;
}

const reviewList: ReviewProps[] = [
  {
    image: "https://randomuser.me/api/portraits/men/32.jpg",
    name: "Budi Santoso",
    userName: "Manajer Proyek",
    comment:
      "Aplikasi ini sangat membantu pekerjaan saya sehari-hari. Fitur-fiturnya lengkap dan mudah digunakan.",
    rating: 5.0,
  },
  {
    image: "https://randomuser.me/api/portraits/women/44.jpg",
    name: "Siti Rahmawati",
    userName: "Pengusaha",
    comment:
      "Saya sangat puas dengan layanan dan kemudahan yang diberikan. Proses pembuatan invoice jadi jauh lebih cepat.",
    rating: 4.9,
  },
  {
    image: "https://randomuser.me/api/portraits/men/65.jpg",
    name: "Agus Pratama",
    userName: "Pengusaha",
    comment:
      "Desainnya modern dan responsif. Sangat cocok untuk kebutuhan bisnis saya.",
    rating: 5.0,
  },
  {
    image: "https://randomuser.me/api/portraits/women/68.jpg",
    name: "Dewi Lestari",
    userName: "Freelancer",
    comment:
      "Saya merekomendasikan aplikasi ini untuk siapa saja yang ingin mengelola invoice dengan mudah dan efisien.",
    rating: 4.8,
  },
];
</script>

<template>
  <section
    id="testimonials"
    class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        Testimonials
      </h2>

      <!-- <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        Hear What Our 1000+ Clients Say
      </h2> -->
      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        Hear What Our Clients Say
      </h2>
    </div>

    <Carousel
      :opts="{
        align: 'start',
      }"
      class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto"
    >
      <CarouselContent>
        <CarouselItem
          v-for="review in reviewList"
          :key="review.name"
          class="md:basis-1/2 lg:basis-1/3"
        >
          <Card class="bg-muted/50 dark:bg-card">
            <CardContent class="pt-6 pb-0">
              <div class="flex gap-1 pb-6">
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
              </div>

              "{{ review.comment }}"
            </CardContent>

            <CardHeader>
              <div class="flex flex-row items-center gap-4">
                <!-- <Avatar>
                  <AvatarImage
                    src="https://www.radix-vue.com/logo.svg"
                    alt="@radix-vue"
                  />
                  <AvatarFallback>SV</AvatarFallback>
                </Avatar> -->

                <div class="flex flex-col">
                  <CardTitle class="text-lg">{{ review.name }}</CardTitle>
                  <CardDescription>{{ review.userName }}</CardDescription>
                </div>
              </div>
            </CardHeader>
          </Card>
        </CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  </section>
</template>
