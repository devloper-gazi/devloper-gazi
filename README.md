"use client";
import { motion } from "framer-motion";
import { Typewriter } from "react-simple-typewriter";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";

export default function PortfolioPage() {
  return (
    <main className="flex flex-col min-h-screen bg-gradient-to-br from-cyan-400 via-sky-300 to-emerald-200 dark:from-[#0d1117] dark:via-[#0d1117] dark:to-[#0d1117]">
      {/* Hero */}
      <section
        className="relative flex flex-col items-center justify-center flex-1 px-6 py-20 text-center text-neutral-800 dark:text-neutral-100"
      >
        <motion.h1
          initial={{ opacity: 0, y: 40 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.8 }}
          className="text-5xl font-extrabold leading-tight sm:text-6xl lg:text-7xl"
          style={{
            background:
              "linear-gradient(90deg, rgba(18,216,250,1) 0%, rgba(166,255,203,1) 100%)",
            WebkitBackgroundClip: "text",
            WebkitTextFillColor: "transparent",
          }}
        >
          Mahmut Gazi Güzel
        </motion.h1>
        <motion.p
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ delay: 0.3, duration: 0.8 }}
          className="mt-4 text-2xl font-semibold"
        >
          <Typewriter
            words={[
              "Researcher Student",
              "AI & Quantum Computing Enthusiast",
              "Photonic Computing Pioneer",
            ]}
            loop={false}
            cursor
            cursorStyle="_"
            typeSpeed={70}
            deleteSpeed={50}
            delaySpeed={2000}
          />
        </motion.p>
        <motion.div
          initial={{ opacity: 0, scale: 0.9 }}
          animate={{ opacity: 1, scale: 1 }}
          transition={{ delay: 0.6, duration: 0.6 }}
          className="mt-8 flex gap-4"
        >
          <Button size="lg">Contact Me</Button>
          <Button variant="secondary" size="lg">
            Download CV
          </Button>
        </motion.div>
      </section>

      {/* About */}
      <section className="relative z-10 w-full bg-white/60 backdrop-blur-lg dark:bg-[#0d1117]/60 py-20 px-6">
        <div className="mx-auto max-w-4xl">
          <h2 className="text-4xl font-bold mb-6 text-center">About Me</h2>
          <p className="text-lg leading-relaxed text-neutral-800 dark:text-neutral-300">
            🔬 I’m a <strong>Researcher Student</strong> exploring the intersection of
            <strong> AI</strong>, <strong>Quantum Computing</strong>, and
            <strong> Photonics</strong>. <br />🚀 I build intelligent systems
            that bridge theoretical physics with practical applications. <br />📚
            Recently published: <em>“From Ether to Algorithms: The Lightborne
            Future of Information Systems”</em>.<br />⚡ Currently focused on
            <strong> Multi‑Agent AI</strong>, <strong>Photonic Computing</strong>, and
            <strong> Ethical Trading Systems</strong>.
          </p>
        </div>
      </section>

      {/* Tech Stack */}
      <section className="py-20 px-6 bg-gradient-to-tr from-emerald-200 via-cyan-200 to-sky-200 dark:bg-[#0d1117]">
        <div className="mx-auto max-w-6xl">
          <h2 className="text-4xl font-bold text-center mb-10">Tech Arsenal</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            <Card className="bg-white/70 dark:bg-[#161B22]">
              <CardContent className="p-6 flex flex-col items-center gap-4">
                <h3 className="text-2xl font-semibold mb-2">🎯 Core Languages</h3>
                <img
                  src="https://skillicons.dev/icons?i=python,rust,js,ts,go,cpp&perline=3"
                  alt="Core Languages"
                />
              </CardContent>
            </Card>
            <Card className="bg-white/70 dark:bg-[#161B22]">
              <CardContent className="p-6 flex flex-col items-center gap-4">
                <h3 className="text-2xl font-semibold mb-2">🛠️ Frameworks & Tools</h3>
                <img
                  src="https://skillicons.dev/icons?i=pytorch,tensorflow,react,nextjs,docker,kubernetes&perline=3"
                  alt="Frameworks & Tools"
                />
              </CardContent>
            </Card>
          </div>
        </div>
      </section>

      {/* Projects */}
      <section className="py-20 px-6 bg-white dark:bg-[#0d1117]">
        <div className="mx-auto max-w-6xl">
          <h2 className="text-4xl font-bold text-center mb-10">Featured Projects</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            {[
              {
                title: "Decentralized Knowledge Guardian",
                desc: "Rust-powered network for ethical content filtering",
                link: "https://github.com/devloper-gazi/Decentralized-Knowledge-Guardian",
                icon: "https://img.icons8.com/3d-fluency/94/artificial-intelligence.png",
              },
              {
                title: "QuantumBreaths1D",
                desc: "BEC simulation in periodic optical lattices",
                link: "https://github.com/devloper-gazi/QuantumBreaths1D",
                icon: "https://img.icons8.com/3d-fluency/94/physics.png",
              },
              {
                title: "FX Trading Bot v0.1",
                desc: "AI-driven algorithmic trading with ethical framework",
                link: "https://github.com/devloper-gazi/Fx_trading_bot_v0.1",
                icon: "https://img.icons8.com/3d-fluency/94/combo-chart.png",
              },
              {
                title: "3D Polariton Condensate",
                desc: "GPU-accelerated quantum fluid dynamics simulation",
                link: "https://github.com/devloper-gazi/3D-Polariton-Condensate-Simulation",
                icon: "https://img.icons8.com/3d-fluency/94/molecule.png",
              },
            ].map((p) => (
              <Card key={p.title} className="bg-white/70 dark:bg-[#161B22]">
                <CardContent className="p-6 flex flex-col items-center text-center gap-4">
                  <img src={p.icon} alt={p.title} className="w-16 h-16" />
                  <h3 className="text-xl font-semibold">{p.title}</h3>
                  <p className="text-base text-neutral-700 dark:text-neutral-400">
                    {p.desc}
                  </p>
                  <Button asChild>
                    <a href={p.link} target="_blank" rel="noopener noreferrer">
                      View Project
                    </a>
                  </Button>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="py-10 bg-gradient-to-tr from-sky-300 to-emerald-300 dark:bg-[#0d1117] text-center text-neutral-800 dark:text-neutral-200">
        <p className="text-lg font-medium">
          "Sometimes it is the people no one can imagine anything of who do the
          things no one can imagine." — Alan Turing
        </p>
        <p className="mt-4">© {new Date().getFullYear()} Mahmut Gazi Güzel</p>
      </footer>
    </main>
  );
}
