<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Paintbrush,
  MessageCircle,
  TabletSmartphone,
  BadgeCheck,
  Goal,
  PictureInPicture,
  MousePointerClick,
  Newspaper,
  ShoppingCart,
  ShoppingBasket,
  CreditCard,
  Users,
  Package,
  Building2,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "shoppingCart",
    title: "Penjualan",
    description:
      "Kelola semua transaksi penjualan dengan sistem invoice otomatis dan laporan real-time",
  },
  {
    icon: "shoppingBasket",
    title: "Pembelian",
    description:
      "Catat dan monitor semua pembelian dengan tracking supplier dan kontrol inventori",
  },
  {
    icon: "creditCard",
    title: "Pembayaran",
    description:
      "Sistem pembayaran terintegrasi dengan multiple metode pembayaran dan reminder otomatis",
  },
  {
    icon: "users",
    title: "Customer",
    description:
      "Database customer lengkap dengan riwayat transaksi dan analisis perilaku pembelian",
  },
  {
    icon: "building2",
    title: "Supplier",
    description:
      "Manajemen supplier terpusat dengan evaluasi performa dan kontrak kerjasama",
  },
  {
    icon: "package",
    title: "Produk",
    description:
      "Katalog produk dengan manajemen stok, harga dinamis, dan kategori yang fleksibel",
  },
];

const iconMap: Record<
  string,
  | typeof TabletSmartphone
  | typeof BadgeCheck
  | typeof Goal
  | typeof PictureInPicture
  | typeof Paintbrush
  | typeof MousePointerClick
  | typeof MessageCircle
  | typeof Newspaper
  | typeof ShoppingCart
  | typeof ShoppingBasket
  | typeof CreditCard
  | typeof Users
  | typeof Package
  | typeof Building2
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
  shoppingCart: ShoppingCart,
  shoppingBasket: ShoppingBasket,
  creditCard: CreditCard,
  users: Users,
  package: Package,
  building2: Building2,
};
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Features
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Fitur Lengkap untuk Bisnis Anda
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Semua yang Anda butuhkan untuk mengelola bisnis dalam satu aplikasi
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        v-for="{ icon, title, description } in featureList"
        :key="title"
      >
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex justify-center items-center">
            <div
              class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4"
            >
              <component
                :is="iconMap[icon]"
                class="size-6 text-primary"
              />
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
