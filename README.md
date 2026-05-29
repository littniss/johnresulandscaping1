# johnresulandscaping1
import React, { useState } from "react";
import { motion } from "framer-motion";
import { Phone, Mail, MapPin, Leaf, Scissors, Truck, Star, CheckCircle2, Menu, X } from "lucide-react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";

const services = [
  {
    icon: Scissors,
    title: "Lawn Mowing",
    text: "Clean, consistent cuts for small yards, larger properties, and 1–10 acre lawns.",
  },
  {
    icon: Leaf,
    title: "Mulch & Bed Edging",
    text: "Fresh mulch, sharp natural edges, weed cleanup, and simple landscape refreshes.",
  },
  {
    icon: Truck,
    title: "Brush & Junk Hauling",
    text: "Yard debris, small cleanouts, sticks, brush piles, and light junk removal.",
  },
];

const gallery = [
  "Fresh mulch bed install",
  "Clean mowing stripes",
  "Property cleanup",
  "Sharp edge detail",
];

const reviews = [
  "Showed up on time and made the yard look clean again.",
  "Great attention to detail and fair pricing.",
  "Fast response and professional work.",
];

export default function LandscapingWebsite() {
  const [menuOpen, setMenuOpen] = useState(false);

  const navItems = ["Services", "Work", "Reviews", "Contact"];

  return (
    <div className="min-h-screen bg-neutral-950 text-white">
      <header className="sticky top-0 z-50 border-b border-white/10 bg-neutral-950/85 backdrop-blur">
        <div className="mx-auto flex max-w-7xl items-center justify-between px-5 py-4">
          <a href="#home" className="flex items-center gap-3">
            <div className="flex h-11 w-11 items-center justify-center rounded-2xl bg-green-500 shadow-lg shadow-green-500/20">
              <Leaf className="h-6 w-6 text-neutral-950" />
            </div>
            <div>
              <p className="text-lg font-black tracking-tight">John Resu Landscaping</p>
              <p className="text-xs text-neutral-400">Lawn Care • Mulch • Cleanup</p>
            </div>
          </a>

          <nav className="hidden items-center gap-8 md:flex">
            {navItems.map((item) => (
              <a key={item} href={`#${item.toLowerCase()}`} className="text-sm font-medium text-neutral-300 transition hover:text-green-400">
                {item}
              </a>
            ))}
          </nav>

          <a href="tel:4432028030" className="hidden md:block">
            <Button className="rounded-2xl bg-green-500 px-5 font-bold text-neutral-950 hover:bg-green-400">
              Get a Free Quote
            </Button>
          </a>

          <button className="md:hidden" onClick={() => setMenuOpen(!menuOpen)} aria-label="Open menu">
            {menuOpen ? <X /> : <Menu />}
          </button>
        </div>

        {menuOpen && (
          <div className="border-t border-white/10 bg-neutral-950 px-5 pb-5 md:hidden">
            <div className="flex flex-col gap-4 pt-4">
              {navItems.map((item) => (
                <a key={item} href={`#${item.toLowerCase()}`} onClick={() => setMenuOpen(false)} className="text-neutral-300">
                  {item}
                </a>
              ))}
              <a href="tel:4432028030">
                <Button className="w-full rounded-2xl bg-green-500 font-bold text-neutral-950 hover:bg-green-400">
                  Call for Quote
                </Button>
              </a>
            </div>
          </div>
        )}
      </header>

      <main id="home">
        <section className="relative overflow-hidden">
          <div className="absolute inset-0 bg-[radial-gradient(circle_at_top_left,rgba(34,197,94,0.28),transparent_38%),radial-gradient(circle_at_bottom_right,rgba(255,255,255,0.08),transparent_30%)]" />
          <div className="relative mx-auto grid max-w-7xl items-center gap-12 px-5 py-20 md:grid-cols-2 md:py-28">
            <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }}>
              <div className="mb-5 inline-flex rounded-full border border-green-400/30 bg-green-400/10 px-4 py-2 text-sm font-semibold text-green-300">
                Serving Baltimore County & nearby areas
              </div>
              <h1 className="text-5xl font-black leading-tight tracking-tight md:text-7xl">
                Make your yard look clean, sharp, and ready for summer.
              </h1>
              <p className="mt-6 max-w-xl text-lg leading-8 text-neutral-300">
                Reliable lawn mowing, mulch beds, edging, seasonal cleanups, and light hauling for homeowners who want the job done right.
              </p>
              <div className="mt-8 flex flex-col gap-4 sm:flex-row">
                <a href="#contact">
                  <Button className="h-12 rounded-2xl bg-green-500 px-7 text-base font-black text-neutral-950 hover:bg-green-400">
                    Request a Quote
                  </Button>
                </a>
                <a href="#services">
                  <Button variant="outline" className="h-12 rounded-2xl border-white/20 bg-white/5 px-7 text-base font-bold text-white hover:bg-white/10">
                    See Services
                  </Button>
                </a>
              </div>
              <div className="mt-8 grid max-w-lg grid-cols-3 gap-4 text-center">
                <div className="rounded-2xl border border-white/10 bg-white/5 p-4">
                  <p className="text-2xl font-black text-green-400">Free</p>
                  <p className="text-xs text-neutral-400">Estimates</p>
                </div>
                <div className="rounded-2xl border border-white/10 bg-white/5 p-4">
                  <p className="text-2xl font-black text-green-400">Local</p>
                  <p className="text-xs text-neutral-400">Service</p>
                </div>
                <div className="rounded-2xl border border-white/10 bg-white/5 p-4">
                  <p className="text-2xl font-black text-green-400">Clean</p>
                  <p className="text-xs text-neutral-400">Results</p>
                </div>
              </div>
            </motion.div>

            <motion.div initial={{ opacity: 0, scale: 0.96 }} animate={{ opacity: 1, scale: 1 }} transition={{ duration: 0.6, delay: 0.1 }}>
              <div className="rounded-[2rem] border border-white/10 bg-white/5 p-4 shadow-2xl shadow-black/40">
                <div className="flex min-h-[440px] flex-col justify-end rounded-[1.5rem] bg-gradient-to-br from-green-800 via-neutral-800 to-neutral-950 p-6">
                  <div className="rounded-3xl bg-neutral-950/75 p-6 backdrop-blur">
                    <p className="text-sm font-bold uppercase tracking-[0.25em] text-green-300">Featured Service</p>
                    <h2 className="mt-3 text-3xl font-black">Mulch Bed Refresh</h2>
                    <p className="mt-3 text-neutral-300">
                      Natural edge, weed removal, fresh mulch, and a clean final blow-off so the whole front yard pops.
                    </p>
                    <div className="mt-5 flex items-center gap-2 text-sm text-green-300">
                      <CheckCircle2 className="h-5 w-5" /> Fast estimates available by text
                    </div>
                  </div>
                </div>
              </div>
            </motion.div>
          </div>
        </section>

        <section id="services" className="mx-auto max-w-7xl px-5 py-20">
          <div className="max-w-2xl">
            <p className="text-sm font-black uppercase tracking-[0.3em] text-green-400">Services</p>
            <h2 className="mt-3 text-4xl font-black tracking-tight md:text-5xl">What we can handle</h2>
            <p className="mt-4 text-neutral-300">Start with one service or bundle multiple together for a cleaner property.</p>
          </div>
          <div className="mt-10 grid gap-6 md:grid-cols-3">
            {services.map((service) => {
              const Icon = service.icon;
              return (
                <Card key={service.title} className="rounded-3xl border-white/10 bg-white/[0.06] text-white shadow-xl shadow-black/20">
                  <CardContent className="p-7">
                    <div className="mb-6 flex h-14 w-14 items-center justify-center rounded-2xl bg-green-500 text-neutral-950">
                      <Icon className="h-7 w-7" />
                    </div>
                    <h3 className="text-2xl font-black">{service.title}</h3>
                    <p className="mt-3 leading-7 text-neutral-300">{service.text}</p>
                  </CardContent>
                </Card>
              );
            })}
          </div>
        </section>

        <section className="bg-white py-20 text-neutral-950" id="work">
          <div className="mx-auto max-w-7xl px-5">
            <div className="flex flex-col justify-between gap-6 md:flex-row md:items-end">
              <div>
                <p className="text-sm font-black uppercase tracking-[0.3em] text-green-700">Recent Work</p>
                <h2 className="mt-3 text-4xl font-black tracking-tight md:text-5xl">Built to look good from the street</h2>
              </div>
              <p className="max-w-lg text-neutral-600">Replace these boxes with real before-and-after photos once you have them.</p>
            </div>
            <div className="mt-10 grid gap-5 md:grid-cols-4">
              {gallery.map((item, index) => (
                <div key={item} className="group overflow-hidden rounded-3xl bg-neutral-100 shadow-lg">
                  <div className="flex h-64 items-end bg-gradient-to-br from-green-700 via-green-500 to-neutral-800 p-5 transition duration-300 group-hover:scale-[1.03]">
                    <div className="rounded-2xl bg-white/90 p-4 shadow-lg backdrop-blur">
                      <p className="text-xs font-black text-green-800">PROJECT {index + 1}</p>
                      <p className="mt-1 font-black">{item}</p>
                    </div>
                  </div>
                </div>
              ))}
            </div>
          </div>
        </section>

        <section id="reviews" className="mx-auto max-w-7xl px-5 py-20">
          <div className="grid gap-10 md:grid-cols-[0.8fr_1.2fr] md:items-center">
            <div>
              <p className="text-sm font-black uppercase tracking-[0.3em] text-green-400">Reviews</p>
              <h2 className="mt-3 text-4xl font-black tracking-tight md:text-5xl">Good work gets noticed.</h2>
              <p className="mt-4 text-neutral-300">Add real customer reviews here as you finish more jobs.</p>
            </div>
            <div className="grid gap-4">
              {reviews.map((review) => (
                <Card key={review} className="rounded-3xl border-white/10 bg-white/[0.06] text-white">
                  <CardContent className="flex gap-4 p-6">
                    <div className="flex gap-1 pt-1 text-green-400">
                      {[1, 2, 3, 4, 5].map((star) => (
                        <Star key={star} className="h-4 w-4 fill-current" />
                      ))}
                    </div>
                    <p className="text-neutral-200">“{review}”</p>
                  </CardContent>
                </Card>
              ))}
            </div>
          </div>
        </section>

        <section id="contact" className="bg-green-500 py-20 text-neutral-950">
          <div className="mx-auto grid max-w-7xl gap-10 px-5 md:grid-cols-2 md:items-center">
            <div>
              <p className="text-sm font-black uppercase tracking-[0.3em] text-green-950/70">Get a Quote</p>
              <h2 className="mt-3 text-4xl font-black tracking-tight md:text-6xl">Send a photo. Get a fast estimate.</h2>
              <p className="mt-5 max-w-xl text-lg font-medium text-green-950/80">
                Text your name, address, and a few photos of the yard or mulch bed. We’ll reply with availability and a price range.
              </p>
            </div>
            <Card className="rounded-[2rem] border-0 bg-neutral-950 text-white shadow-2xl shadow-green-950/30">
              <CardContent className="space-y-5 p-8">
                <a href="tel:4432028030" className="flex items-center gap-4 rounded-2xl bg-white/5 p-4 transition hover:bg-white/10">
                  <Phone className="h-6 w-6 text-green-400" />
                  <div>
                    <p className="text-sm text-neutral-400">Call/Text</p>
                    <p className="text-xl font-black">(443) 202-8030</p>
                  </div>
                </a>
                <a href="mailto:jackresu27@outlook.com" className="flex items-center gap-4 rounded-2xl bg-white/5 p-4 transition hover:bg-white/10">
                  <Mail className="h-6 w-6 text-green-400" />
                  <div>
                    <p className="text-sm text-neutral-400">Email</p>
                    <p className="text-xl font-black">jackresu27@outlook.com</p>
                  </div>
                </a>
                <div className="flex items-center gap-4 rounded-2xl bg-white/5 p-4">
                  <MapPin className="h-6 w-6 text-green-400" />
                  <div>
                    <p className="text-sm text-neutral-400">Service Area</p>
                    <p className="text-xl font-black">Baltimore County, MD</p>
                  </div>
                </div>
                <Button className="h-13 w-full rounded-2xl bg-green-500 py-6 text-lg font-black text-neutral-950 hover:bg-green-400">
                  Text for a Free Estimate
                </Button>
              </CardContent>
            </Card>
          </div>
        </section>
      </main>

      <footer className="border-t border-white/10 bg-neutral-950 px-5 py-8 text-center text-sm text-neutral-400">
        <p>© 2026 John Resu Landscaping. Lawn care, mulch, edging, and cleanups.</p>
      </footer>
    </div>
  );
}
