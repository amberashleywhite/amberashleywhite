import React from "react"; import { motion } from "framer-motion"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button";

const images = [ { src: "/mnt/data/a_digital_photograph_captures_a_blonde_woman_with.png", title: "Street Style Editorial", }, { src: "/mnt/data/a_digital_photograph_features_a_blonde_female_mode.png", title: "Runway Walk", }, { src: "/mnt/data/winter_pose_left.png", title: "Winter Editorial", }, { src: "/mnt/data/winter_pose_right.png", title: "Winter Close-Up", }, ];

export default function ModelPortfolio() { return ( <div className="min-h-screen bg-neutral-100 text-neutral-900"> {/* Hero Section */} <section className="relative h-[80vh] flex items-center justify-center bg-black text-white overflow-hidden"> <img
src="/mnt/data/a_digital_photograph_captures_a_blonde_woman_with.png"
alt="Model Hero"
className="absolute inset-0 w-full h-full object-cover opacity-60"
/> <div className="relative z-10 text-center px-6"> <motion.h1 initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.8 }} className="text-4xl md:text-6xl font-semibold tracking-wide" > Amber Ashley White </motion.h1> <p className="mt-4 text-lg md:text-xl text-neutral-200"> Amber Ashley White - Fashion Model </p> <Button className="mt-6 rounded-2xl px-6 py-2 text-base"> View Portfolio </Button> </div> </section>

{/* About Section */}
  <section className="max-w-5xl mx-auto px-6 py-16 grid md:grid-cols-2 gap-10 items-center">
    <img
      src="/mnt/data/a_digital_photograph_features_a_blonde_female_mode.png"
      alt="Model"
      className="rounded-2xl shadow-lg object-cover w-full h-full"
    />
    <div>
      <h2 className="text-3xl font-semibold mb-4">About the Model</h2>
      <p className="text-neutral-700 leading-relaxed">
        A versatile fashion model specializing in runway, editorial, and
        street-style photography. Known for expressive presence, elegant
        posture, and a refined contemporary aesthetic suitable for global
        fashion campaigns and high-end editorials.
      </p>
      <div className="mt-6 flex gap-4">
        <Button className="rounded-2xl">Download Portfolio</Button>
        <Button variant="outline" className="rounded-2xl">
          Contact
        </Button>
      </div>
    </div>
  </section>

  {/* Gallery Section */}
  <section className="bg-white py-16">
    <div className="max-w-6xl mx-auto px-6">
      <h2 className="text-3xl font-semibold mb-10 text-center">
        Portfolio Highlights
      </h2>
      <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
        {images.map((img, index) => (
          <motion.div
            key={index}
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.6, delay: index * 0.1 }}
            viewport={{ once: true }}
          >
            <Card className="rounded-2xl overflow-hidden shadow-md hover:shadow-xl transition">
              <CardContent className="p-0">
                <img
                  src={img.src}
                  alt={img.title}
                  className="w-full h-72 object-cover"
                />
                <div className="p-4">
                  <p className="text-sm font-medium">{img.title}</p>
                </div>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>
    </div>
  </section>

  {/* Contact Section */}
  <section className="bg-neutral-900 text-white py-16">
    <div className="max-w-4xl mx-auto px-6 text-center">
      <h2 className="text-3xl font-semibold mb-4">Book the Model</h2>
      <p className="text-neutral-300 mb-8">
        Available for runway shows, brand campaigns, editorials, and fashion
        collaborations worldwide.
      </p>
      <Button className="rounded-2xl px-8 py-3 text-base">
        Contact & Bookings
      </Button>
    </div>
  </section>

  {/* Footer */}
  <footer className="bg-black text-neutral-400 text-center py-6 text-sm">
    © {new Date().getFullYear()} Model Portfolio. All rights reserved.
  </footer>
</div>

); }
