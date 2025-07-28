<script setup lang="ts">
import { Button } from "@/components/ui/button";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import { Check } from "lucide-vue-next";

enum PopularPlan {
  NO = 0,
  YES = 1,
}

interface PlanProps {
  title: string;
  popular: PopularPlan;
  price: string;
  description: string;
  buttonText: string;
  benefitList: string[];
}

const plans: PlanProps[] = [
  {
    title: "Starter",
    popular: 1,
    price: "Gratis",
    description:
      "Perfect untuk umkm yang baru memulai",
    buttonText: "Daftar Sekarang",
    benefitList: [
      "Full feature access ke semua halaman",
      "Manajemen penjualan & pembelian",
      "Manajemen pembayaran", 
      "Manajemen keuangan",
      "Database customer & supplier",
      "Manajemen produk & inventori",
      "Import data massal",
      "Laporan & analisis real-time",
      "Support email 24/7",
      "Data backup otomatis",
      "5 pengguna",
      "1 Perusahaan",
    ],
  },
  // {
  //   title: "Premium",
  //   popular: 0,
  //   price: 45,
  //   description:
  //     "Lorem ipsum dolor sit, amet ipsum consectetur adipisicing elit.",
  //   buttonText: "Get starterd",
  //   benefitList: [
  //     "4 team member",
  //     "8 GB storage",
  //     "Upto 6 pages",
  //     "Priority support",
  //     "AI assistance",
  //   ],
  // },
  // {
  //   title: "Enterprise",
  //   popular: 0,
  //   price: 120,
  //   description:
  //     "Lorem ipsum dolor sit, amet ipsum consectetur adipisicing elit.",
  //   buttonText: "Contact US",
  //   benefitList: [
  //     "10 team member",
  //     "20 GB storage",
  //     "Upto 10 pages",
  //     "Phone & email support",
  //     "AI assistance",
  //   ],
  // },
];
</script>

<template>
  <section id="pricing" class="container py-24 sm:py-32">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Pricing
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Paket Berlangganan
    </h2>

    <h3
      class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground pb-14"
    >
      Pilih paket yang sesuai dengan kebutuhan bisnis Anda
    </h3>

    <!-- <div class="grid md:grid-cols-2 lg:grid-cols-3  gap-8 lg:gap-4"> ini untuk paket langganan lebih dari 1 -->
    <div class="grid lg:grid-cols-3  gap-8 lg:gap-4">
      <Card
        v-for="{
          title,
          popular,
          price,
          description,
          buttonText,
          benefitList,
        } in plans"
        :key="title"
        class="lg:col-start-2"
        :class="{
          'drop-shadow-xl shadow-black/10 dark:shadow-white/10 border-[1.5px] border-primary lg:scale-[1.1] ':
            popular === PopularPlan?.YES,
        }"
      >
        <CardHeader>
          <CardTitle class="pb-2">
            {{ title }}
          </CardTitle>

          <CardDescription class="pb-4">{{ description }}</CardDescription>

          <div>
            <!-- <span class="text-3xl font-bold">Rp{{ price }}</span>
            <span class="text-muted-foreground"> /bulan</span><br />
            <span class="text-xs  text-red-500">*30 Hari Uji Coba Gratis</span> -->
            <span class="text-3xl font-bold">{{ price }}</span>
          </div>
        </CardHeader>

        <CardContent class="flex">
          <div class="space-y-4">
            <span
              v-for="benefit in benefitList"
              :key="benefit"
              class="flex"
            >
              <Check class="text-primary mr-2" />
              <h3>{{ benefit }}</h3>
            </span>
          </div>
        </CardContent>

        <CardFooter>
            <Button
            :variant="popular === PopularPlan?.NO ? 'secondary' : 'default'"
            class="w-full"
            as="a"
            href="https://app.invoicemu.com/"
            target="_blank"
            rel="noopener"
            >
            {{ buttonText }}
            </Button>
        </CardFooter>
      </Card>
    </div>
  </section>
</template>
