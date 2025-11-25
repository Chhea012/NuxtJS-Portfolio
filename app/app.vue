<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900 text-white antialiased overflow-hidden">
    <!-- Animated background -->
    <div class="fixed inset-0 overflow-hidden pointer-events-none">
      <div class="absolute top-20 right-10 w-96 h-96 bg-indigo-500/10 rounded-full blur-3xl animate-pulse"></div>
      <div class="absolute bottom-20 left-10 w-72 h-72 bg-cyan-500/10 rounded-full blur-3xl animate-pulse delay-1000"></div>
    </div>

    <!-- Navigation -->
    <header class="fixed w-full z-40 bg-slate-900/80 backdrop-blur-xl border-b border-white/10">
      <div class="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between">
        <a href="#home" class="flex items-center gap-3 group">
          <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-indigo-500 via-cyan-500 to-teal-500 overflow-hidden shadow-lg group-hover:shadow-indigo-500/50 transition">
            <img src="./assets/images/chhea.jpg" alt="Chhea Chhouy" class="w-full h-full object-cover">
          </div>
          <div>
            <div class="text-lg font-bold">CHHEA CHHOUY</div>
            <div class="text-xs text-cyan-400">Full-Stack Developer</div>
          </div>
        </a>

        <nav class="hidden md:flex items-center gap-10 text-base font-semibold tracking-wide">
          <a href="#about" class="relative text-gray-300 hover:text-cyan-400 transition after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-cyan-400 after:transition-all after:duration-300 hover:after:w-full">ABOUT</a>
          <a href="#skills" class="relative text-gray-300 hover:text-cyan-400 transition after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-cyan-400 after:transition-all after:duration-300 hover:after:w-full">SKILLS</a>
          <a href="#projects" class="relative text-gray-300 hover:text-cyan-400 transition after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-cyan-400 after:transition-all after:duration-300 hover:after:w-full">PROJECTS</a>
          <a href="#contact" class="relative text-gray-300 hover:text-cyan-400 transition after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-cyan-400 after:transition-all after:duration-300 hover:after:w-full">CONTACT</a>

          <button @click="downloadCV" class="download-cv-btn ">
            <span class="button_lg">
              <span class="button_sl"></span>
              <span class="button_text tracking-wider">Download CV</span>
            </span>
          </button>
        </nav>

        <button @click="open = !open" class="md:hidden p-2 rounded-lg border border-white/20 hover:bg-white/10 transition">
          <svg v-if="!open" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
          <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>

      <transition name="slide">
        <div v-if="open" class="md:hidden bg-slate-900/95 backdrop-blur-xl border-t border-white/10">
          <div class="px-6 py-6 space-y-4">
            <a href="#about" @click="open=false" class="block py-2 text-lg hover:text-cyan-400">About</a>
            <a href="#skills" @click="open=false" class="block py-2 text-lg hover:text-cyan-400">Skills</a>
            <a href="#projects" @click="open=false" class="block py-2 text-lg hover:text-cyan-400">Projects</a>
            <a href="#contact" @click="open=false" class="block py-2 text-lg hover:text-cyan-400">Contact</a>
            <button @click="downloadCV(); open=false" class="download-cv-btn w-full">
              <span class="button_lg">
                <span class="button_sl"></span>
                <span class="button_text">Download CV</span>
              </span>
            </button>
          </div>
        </div>
      </transition>
    </header>

    <main class="pt-20 relative z-10">
      <!-- Hero Section with Orbiting Skills -->
      <section id="home" class="max-w-7xl mx-auto px-6 py-20 md:py-32">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div class="space-y-8">
            <div>
              <span class="inline-block px-4 py-2 bg-cyan-500/10 border border-cyan-500/30 rounded-full text-sm font-medium text-cyan-400">
                Full-Stack Web Developer • IT Programming
              </span>
              <h1 class="mt-4 text-5xl md:text-7xl font-bold leading-tight">
              <span class="bg-gradient-to-r from-white via-cyan-200 to-indigo-400 bg-clip-text text-transparent">
                <!-- The visible typing text -->
                <span class="typing-text">{{ displayedText }}</span>
                <!-- Blinking cursor -->
                <span class="cursor"></span>
              </span>
            </h1>
            </div>

            <p class="text-lg text-slate-300 leading-relaxed max-w-2xl">
              Passionate Full-Stack Developer from Siem Reap, Cambodia. Currently an <strong>IT Programming Intern at The NGO Forum on Cambodia</strong>, building real-world automation systems with Python, Laravel, and AWS.
            </p>

            <div class="flex flex-wrap gap-4 items-center">
              <button @click="downloadCV" class="download-cv-btn">
                <span class="button_lg">
                  <span class="button_sl"></span>
                  <span class="button_text flex items-center gap-2">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"/>
                    </svg>
                    Download CV
                  </span>
                </span>
              </button>

              <a href="#projects" class="px-7 py-4 border border-cyan-500/40 hover:bg-cyan-500/10 font-semibold transition">
                View Projects
              </a>
            </div>

            <div class="pt-6 space-y-3 text-slate-400">
              <div class="flex items-center gap-3">
                <svg class="w-5 h-5 text-cyan-400" fill="currentColor" viewBox="0 0 20 20"><path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"/><path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"/></svg>
                <span>{{ contact.email }}</span>
              </div>
              <div class="flex items-center gap-3">
                <svg class="w-5 h-5 text-cyan-400" fill="currentColor" viewBox="0 0 20 20"><path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773c.058.319.227.635.437.802.21.166.519.27.82.27.3 0 .609-.104.82-.27.21-.167.379-.483.437-.802l1.548.773a1 1 0 01.54 1.06l-.74 4.435A1 1 0 0110.153 17H8a1 1 0 01-1-1v-1a6 6 0 00-6-6V3z"/></svg>
                <span>{{ contact.phone }}</span>
              </div>
            </div>
          </div>

          <!-- ORBITING SKILLS AROUND PROFILE -->
          <div class="relative w-96 h-96 mx-auto group">
            <!-- Outer Glow Ring -->
            <div class="absolute -inset-8 bg-gradient-to-r from-cyan-500 via-purple-600 to-indigo-500 rounded-full blur-3xl opacity-50 group-hover:opacity-80 group-hover:scale-110 transition duration-1000"></div>

            <!-- Profile Picture -->
            <div class="relative w-full h-full rounded-full p-3 bg-gradient-to-br from-indigo-600 via-cyan-500 to-teal-500 shadow-2xl">
              <div class="w-full h-full rounded-full overflow-hidden bg-slate-900 p-2">
                <img src="./assets/images/chhea.jpg" alt="Chhea Chhouy" class="w-full h-full rounded-full object-cover border-4 border-slate-900">
              </div>
            </div>

            <!-- Orbiting Icons -->
            <div class="absolute inset-0">
              <div class="orbit-container">
                <div v-for="(skill, index) in skills" :key="skill.name" class="orbit-item" :style="{ '--i': index }">
                  <div class="icon-wrapper group/icon">
                    <img :src="skill.icon" :alt="skill.name" class="w-14 h-14 drop-shadow-2xl transition-all duration-300 group-hover/icon:scale-150">
                    <span class="tooltip">{{ skill.name }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- About -->
      <section id="about" class="max-w-7xl mx-auto px-6 py-20">
        <div class="bg-slate-800/50 backdrop-blur-xl rounded-3xl p-10 border border-white/10">
          <h2 class="text-4xl font-bold mb-8 bg-gradient-to-r from-cyan-400 to-indigo-400 bg-clip-text text-transparent">About Me</h2>
          <p class="text-lg text-slate-300 leading-relaxed mb-10">
            I'm a dedicated Full-Stack Developer with hands-on experience in building production-ready web applications. Currently interning at <strong>The NGO Forum on Cambodia</strong>, where I'm developing automation tools used by real organizations.
          </p>

          <div class="grid md:grid-cols-2 gap-10">
            <div>
              <h3 class="text-xl font-bold text-cyan-400 mb-5">Experience</h3>
              <ul class="space-y-4 text-slate-300">
                <li class="flex gap-3"><span class="text-indigo-400">→</span> <strong>IT Intern (Full-Stack)</strong> — The NGO Forum on Cambodia (Aug 2025 – Feb 2026)</li>
                <li class="flex gap-3"><span class="text-indigo-400">→</span> Scrum Master & Developer — POS System (Virtual Company)</li>
                <li class="flex gap-3"><span class="text-indigo-400">→</span> Team Lead — Multiple front-end & Python projects</li>
              </ul>
            </div>
            <div>
              <h3 class="text-xl font-bold text-cyan-400 mb-5">Education</h3>
              <div class="space-y-5 text-slate-300">
                <div>
                  <div class="font-bold text-white">Associate Degree in Web Programming</div>
                  <div>Passerelles Numériques Cambodia • 2024 – Present</div>
                </div>
                <div>
                  <div class="font-bold text-white">High School Diploma (Bac II)</div>
                  <div>Pouk High School • 2023</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Skills -->
      <section id="skills" class="max-w-7xl mx-auto px-6 py-20">
        <h2 class="text-4xl font-bold mb-12 text-center bg-gradient-to-r from-cyan-400 to-indigo-400 bg-clip-text text-transparent">
          Skills & Expertise
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <!-- Your existing skill cards -->
          <div class="bg-slate-800/50 backdrop-blur-xl rounded-2xl p-8 border border-white/10 hover:border-cyan-500/50 transition">
            <h3 class="text-2xl font-bold text-cyan-400 mb-6 flex items-center gap-3">
              <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/></svg>
              Soft Skills
            </h3>
            <ul class="space-y-3 text-slate-300 text-sm">
              <li class="flex items-center gap-2">• Respect & Professionalism</li>
              <li class="flex items-center gap-2">• Adaptability & Fast Learning</li>
              <li class="flex items-center gap-2">• Clear Communication</li>
              <li class="flex items-center gap-2">• Problem Solving</li>
              <li class="flex items-center gap-2">• Critical Thinking</li>
              <li class="flex items-center gap-2">• Time Management</li>
              <li class="flex items-center gap-2">• Teamwork & Collaboration</li>
            </ul>
          </div>

          <div class="bg-slate-800/50 backdrop-blur-xl rounded-2xl p-8 border border-white/10 hover:border-indigo-500/50 transition">
            <h3 class="text-2xl font-bold text-indigo-400 mb-6 flex items-center gap-3">
              <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/></svg>
              Hard Skills
            </h3>
            <ul class="space-y-3 text-slate-300 text-sm">
              <li>• Vue.js / Nuxt.js</li>
              <li>• React.js</li>
              <li>• JavaScript / TypeScript (OOP)</li>
              <li>• Laravel & PHP (MVC)</li>
              <li>• Python Flask / Django</li>
              <li>• Node.js (REST APIs)</li>
              <li>• MySQL & Firebase</li>
              <li>• HTML / CSS / SASS</li>
              <li>• Bootstrap 5 / Tailwind CSS</li>
              <li>• Algorithm & Data Structures (Python)</li>
              <li>• Data Analytics with Power BI</li>
            </ul>
          </div>

          <div class="bg-slate-800/50 backdrop-blur-xl rounded-2xl p-8 border border-white/10 hover:border-teal-500/50 transition">
            <h3 class="text-2xl font-bold text-teal-400 mb-6 flex items-center gap-3">
              <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"/></svg>
              Tools & DevOps
            </h3>
            <ul class="space-y-3 text-slate-300 text-sm">
              <li>• Git & GitHub</li>
              <li>• Jira & Scrum</li>
              <li>• AWS EC2 / Ubuntu Linux</li>
              <li>• Postman (API Testing)</li>
              <li>• Figma (UI/UX Design)</li>
              <li>• Netlify / Vercel</li>
              <li>• MobaXterm</li>
              <li>• Lucidchart / Draw.io</li>
              <li>• Canva</li>
              <li>• AI Tools (ChatGPT, Gemini, Claude)</li>
              <li>• MS Office (Word, Excel, PowerPoint)</li>
            </ul>
          </div>

          <div class="bg-slate-800/50 backdrop-blur-xl rounded-2xl p-8 border border-white/10 hover:border-purple-500/50 transition">
            <h3 class="text-2xl font-bold text-purple-400 mb-6 flex items-center gap-3">
              <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"/></svg>
              Interests
            </h3>
            <ul class="space-y-3 text-slate-300 text-sm">
              <li>• Volunteering & Community Service</li>
              <li>• Building Personal Projects</li>
              <li>• Reading Tech Articles & Books</li>
              <li>• Learning New Programming Languages</li>
              <li>• Exploring AI & Automation Tools</li>
              <li>• Traveling & Photography</li>
            </ul>
          </div>
        </div>
      </section>

      <!-- Projects -->
      <section id="projects" class="max-w-7xl mx-auto px-6 py-20">
        <h2 class="text-4xl font-bold mb-12 text-center bg-gradient-to-r from-cyan-400 to-indigo-400 bg-clip-text text-transparent">Featured Projects</h2>
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <article v-for="p in projects" :key="p.abbr" class="group relative">
            <div class="absolute -inset-1 bg-gradient-to-r from-indigo-600 to-cyan-600 rounded-2xl blur opacity-0 group-hover:opacity-30 transition duration-700"></div>
            <div class="relative bg-slate-800/70 backdrop-blur-xl rounded-2xl p-6 border border-white/10 hover:border-cyan-500/50 transition">
              <div class="flex items-start justify-between mb-4">
                <div class="w-14 h-14 rounded-xl bg-gradient-to-br from-indigo-500/20 to-cyan-500/20 border border-indigo-500/40 flex items-center justify-center text-2xl font-bold text-indigo-300">
                  {{ p.abbr }}
                </div>
                <span class="text-xs px-3 py-1 bg-white/10 rounded-full">{{ p.date }}</span>
              </div>
              <h3 class="text-xl font-bold mb-2">{{ p.title }}</h3>
              <p class="text-sm text-slate-400 mb-4 line-clamp-3">{{ p.summary }}</p>
              <div class="flex flex-wrap gap-2 mb-5">
                <span v-for="t in p.tech.slice(0, 4)" :key="t" class="text-xs px-2 py-1 bg-white/5 rounded border border-white/10">{{ t }}</span>
                <span v-if="p.tech.length > 4" class="text-xs text-slate-500">+{{ p.tech.length - 4 }} more</span>
              </div>
              <div class="flex gap-3">
                <a v-if="p.repo" :href="p.repo" target="_blank" class="flex items-center gap-2 text-sm font-medium text-indigo-400 hover:text-indigo-300 transition">
                  <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                  Code
                </a>
                <a v-if="p.live" :href="p.live" target="_blank" class="flex items-center gap-2 text-sm font-medium text-cyan-400 hover:text-cyan-300 transition">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"/></svg>
                  Live Demo
                </a>
              </div>
            </div>
          </article>
        </div>
      </section>

      <!-- Responsive Contact Section -->
      <section id="contact" class="max-w-7xl mx-auto px-4 sm:px-6 py-16 sm:py-20">
        <div class="bg-gradient-to-br from-slate-800 via-slate-900 to-slate-800 rounded-3xl p-6 sm:p-10 md:p-16 border border-white/10">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-10 sm:gap-12">

            <!-- Left Side -->
            <div>
              <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold mb-4 sm:mb-6">Let's Work Together</h2>
              <p class="text-base sm:text-lg text-slate-300 mb-8 sm:mb-10">
                I'm open to full-time and freelance project opportunities.
              </p>

              <a :href="'mailto:' + contact.email" class="flex items-center gap-4 text-base sm:text-lg hover:text-cyan-400 transition group mb-6 sm:mb-8">
                <div class="w-10 h-10 sm:w-12 sm:h-12 rounded-lg bg-cyan-500/10 border border-cyan-500/30 flex items-center justify-center group-hover:bg-cyan-500/20 transition">
                  <svg class="w-5 h-5 sm:w-6 sm:h-6 text-cyan-400" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"/>
                    <path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"/>
                  </svg>
                </div>
                <span>{{ contact.email }}</span>
              </a>

              <!-- Social Icons -->
              <div class="flex flex-wrap gap-4 sm:gap-5">
                <a href="https://www.linkedin.com/in/chhea-chhouy-337667374/" target="_blank" class="w-12 h-12 sm:w-14 sm:h-14 rounded-xl bg-white/10 border border-white/20 flex items-center justify-center hover:bg-indigo-500/20 hover:border-indigo-500 transition group">
                  <svg class="w-6 h-6 sm:w-7 sm:h-7 text-indigo-400 group-hover:text-indigo-300" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                </a>

                <a href="https://github.com/Chhea012" target="_blank" class="w-12 h-12 sm:w-14 sm:h-14 rounded-xl bg-white/10 border border-white/20 flex items-center justify-center hover:bg-cyan-500/20 hover:border-cyan-500 transition group">
                  <svg class="w-6 h-6 sm:w-7 sm:h-7 text-cyan-400 group-hover:text-cyan-300" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                </a>

                <a href="https://www.youtube.com/@Chheadeveloper" target="_blank" class="w-12 h-12 sm:w-14 sm:h-14 rounded-xl bg-white/10 border border-white/20 flex items-center justify-center hover:bg-red-500/20 hover:border-red-500 transition group">
                  <svg class="w-6 h-6 sm:w-7 sm:h-7 text-red-500 group-hover:text-red-400" fill="currentColor" viewBox="0 0 24 24"><path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.016 3.016 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.016 3.016 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.75 15.02l-.001-6.04 6.02 3.02-6.019 3.02z"/></svg>
                </a>

                <a href="https://www.facebook.com/profile.php?id=61583208074481" target="_blank" class="w-12 h-12 sm:w-14 sm:h-14 rounded-xl bg-white/10 border border-white/20 flex items-center justify-center hover:bg-blue-500/20 hover:border-blue-500 transition group">
                  <svg class="w-6 h-6 sm:w-7 sm:h-7 text-blue-500 group-hover:text-blue-400" fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385h-3.047v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953h-1.513c-1.491 0-1.956.927-1.956 1.875v2.25h3.328l-.532 3.47h-2.796v8.385c5.737-.9 10.125-5.864 10.125-11.854z"/></svg>
                </a>
              </div>

              <p class="mt-6 sm:mt-8 text-xs sm:text-sm text-slate-500">
                Follow me for coding tutorials, project updates, and tech content
              </p>
            </div>

            <!-- Right Side: Form -->
            <form @submit.prevent="submitContact" class="space-y-4 sm:space-y-6">
              <input v-model="form.name" type="text" placeholder="Your Name" required class="w-full px-5 py-3 sm:px-6 sm:py-4 bg-white/10 border border-white/20 rounded-xl focus:border-cyan-500 focus:outline-none transition text-white placeholder-slate-500">

              <input v-model="form.email" type="email" placeholder="Your Email" required class="w-full px-5 py-3 sm:px-6 sm:py-4 bg-white/10 border border-white/20 rounded-xl focus:border-cyan-500 focus:outline-none transition text-white placeholder-slate-500">

              <textarea v-model="form.message" rows="5" placeholder="Your Message" required class="w-full px-5 py-3 sm:px-6 sm:py-4 bg-white/10 border border-white/20 rounded-xl focus:border-cyan-500 focus:outline-none transition resize-none text-white placeholder-slate-500"></textarea>

              <div class="flex gap-3 sm:gap-4">
                <button type="submit" class="flex-1 px-6 sm:px-8 py-3 sm:py-4 bg-gradient-to-r from-indigo-600 to-cyan-600 rounded-xl font-bold hover:shadow-lg hover:shadow-cyan-500/50 transition text-sm sm:text-base">
                  Send Message
                </button>

                <button type="button" @click="resetForm" class="px-6 sm:px-8 py-3 sm:py-4 border border-white/20 hover:bg-white/10 rounded-xl font-semibold transition text-sm sm:text-base">
                  Clear
                </button>
              </div>

              <p v-if="sent" class="text-green-400 font-bold text-base sm:text-lg">Message sent successfully!</p>
            </form>

          </div>
        </div>
      </section>

      <footer class="text-center py-10 text-slate-500 text-sm border-t border-white/10">
        © {{ new Date().getFullYear() }} Chhea Chhouy. Built with NuxtJS + Tailwind CSS
      </footer>
    </main>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import cvPdf from '@/assets/cv/Chhea Chhouy.pdf'

const open = ref(false)
const sent = ref(false)

const downloadCV = () => {
  const link = document.createElement('a')
  link.href = cvPdf
  link.download = 'Chhea_Chhouy_CV.pdf'
  document.body.appendChild(link)
  link.click()
  document.body.removeChild(link)
}
const fullText = "CHHOUY Chhea"
const displayedText = ref('')
let index = 0
let isDeleting = false
let timer = null

const typeWriter = () => {
  // Full text reached → start deleting after short pause
  if (!isDeleting && index === fullText.length) {
    timer = setTimeout(() => { isDeleting = true; typeWriter() }, 1500)
    return
  }

  // Deleted completely → start typing again
  if (isDeleting && index === 0) {
    isDeleting = false
  }

  // Calculate speed (faster when deleting)
  const speed = isDeleting ? 80 : 150

  // Update displayed text
  displayedText.value = fullText.substring(0, index)

  // Move index forward/backward
  index = isDeleting ? index - 1 : index + 1

  timer = setTimeout(typeWriter, speed)
}

onMounted(() => {
  typeWriter()
})

onUnmounted(() => {
  if (timer) clearTimeout(timer)
})

// ORBITING SKILLS DATA
const skills = [

  // Frontend Stack
  { name: 'HTML', icon: 'https://skillicons.dev/icons?i=html' },
  { name: 'CSS', icon: 'https://skillicons.dev/icons?i=css' },
  { name: 'JavaScript', icon: 'https://skillicons.dev/icons?i=js' },
  { name: 'TypeScript', icon: 'https://skillicons.dev/icons?i=ts' },
  { name: 'Tailwind', icon: 'https://skillicons.dev/icons?i=tailwind' },
  { name: 'Bootstrap', icon: 'https://skillicons.dev/icons?i=bootstrap' },
  { name: 'SASS', icon: 'https://skillicons.dev/icons?i=sass' },
  { name: 'Vue.js', icon: 'https://skillicons.dev/icons?i=vue' },
  { name: 'Nuxt.js', icon: 'https://skillicons.dev/icons?i=nuxtjs' },
  { name: 'React', icon: 'https://skillicons.dev/icons?i=react' },

  // Backend & Full Stack
  { name: 'Node.js', icon: 'https://skillicons.dev/icons?i=nodejs' },
  { name: 'PHP', icon: 'https://skillicons.dev/icons?i=php' },
  { name: 'Laravel', icon: 'https://skillicons.dev/icons?i=laravel' },
  { name: 'Flask', icon: 'https://skillicons.dev/icons?i=flask' },
  { name: 'Python', icon: 'https://skillicons.dev/icons?i=python' },

  // Database & DevOps
  { name: 'MySQL', icon: 'https://skillicons.dev/icons?i=mysql' },
  { name: 'Firebase', icon: 'https://skillicons.dev/icons?i=firebase' },



  // Tools & Platforms
  { name: 'Git', icon: 'https://skillicons.dev/icons?i=git' },
  { name: 'GitHub', icon: 'https://skillicons.dev/icons?i=github' },
  { name: 'AWS', icon: 'https://skillicons.dev/icons?i=aws' },
  { name: 'Linux', icon: 'https://skillicons.dev/icons?i=linux' },
  { name: 'Postman', icon: 'https://skillicons.dev/icons?i=postman' },
  { name: 'Figma', icon: 'https://skillicons.dev/icons?i=figma' },
  { name: 'VS Code', icon: 'https://skillicons.dev/icons?i=vscode' },
]
const contact = reactive({
  email: 'chhea.chhouy@student.passerellesnumeriques.org',
  phone: '+855 67 408 241'
})

const linkedin = 'https://www.linkedin.com/in/chhea-chhouy'
const github = 'https://github.com/Chhea012'

const projects = [
  {
    abbr: 'ASC',
    title: 'Automation System for Contracts',
    date: 'Aug 2025 – Present',
    summary: 'Full-stack platform automating consultant & intern contracts for The NGO Forum on Cambodia. Includes payment tracking, compliance checks, and secure document generation.',
    repo: null,
    live: null,
    tech: ['Python', 'Django', 'Flask', 'AWS EC2', 'Bootstrap', 'Chart.js', 'Figma', 'Jira']
  },
  {
    abbr: 'LMS',
    title: 'Leave Management System',
    date: 'Jul – Aug 2025',
    summary: 'HR system with attendance tracking, leave requests, real-time analytics dashboard, and financial reports. Deployed on AWS.',
    repo: 'https://github.com/yonyen99/LMS',
    live: null,
    tech: ['Laravel', 'Vite', 'MySQL', 'Chart.js', 'AWS EC2', 'Bootstrap']
  },
  {
    abbr: 'POS',
    title: 'Point of Sale System',
    date: 'Mar – Apr 2025',
    summary: 'Full-featured POS with inventory, barcode scanning, sales reports, and Telegram bot notifications. Led as Scrum Master.',
    repo: 'https://github.com/Chhea012/VC1_POS_System',
    live: null,
    tech: ['PHP', 'MySQL', 'Bootstrap', 'Telegram API', 'Chart.js']
  },
  {
    abbr: 'TMA',
    title: 'Task Management App',
    date: 'Jan 2025',
    summary: 'Drag-and-drop task tracker with calendar view and offline sync using Firebase + localStorage.',
    repo: 'https://github.com/Chhea012/Task-Management-App-B12',
    live: null,
    tech: ['JavaScript', 'Firebase', 'SASS', 'Figma']
  },
  {
    abbr: 'SCR',
    title: 'Web Data Scraper',
    date: 'Nov 2024',
    summary: 'Desktop GUI tool to scrape and export web data. Built with Python and led a team of 4.',
    repo: 'https://github.com/Chhea012/webdata-scraper-project',
    live: null,
    tech: ['Python', 'BeautifulSoup', 'Tkinter', 'JSON']
  },
  {
    abbr: 'MBW',
    title: 'Music Band Website',
    date: 'Oct – Nov 2024',
    summary: 'Responsive promotional website for a music band with videos, tour dates, and contact form.',
    repo: 'https://github.com/Chhea012/class_a_music_band',
    live: null,
    tech: ['HTML', 'CSS', 'SASS', 'Figma']
  }
]

const form = reactive({ name: '', email: '', message: '' })

const submitContact = () => {
  console.log('Form submitted:', form)
  sent.value = true
  setTimeout(() => {
    sent.value = false
    form.name = form.email = form.message = ''
  }, 4000)
}

const resetForm = () => {
  form.name = form.email = form.message = ''
}
</script>

<style scoped>
/* ---------- NEW DOWNLOAD CV BUTTON ---------- */
.download-cv-btn {
  appearance: none;
  border: none;
  background: none;
  color: #fff;
  cursor: pointer;
  position: relative;
  padding: 8px;
  text-transform: uppercase;
  font-weight: bold;
  font-size: 14px;
  transition: all 0.15s ease;
}

.download-cv-btn::before,
.download-cv-btn::after {
  content: '';
  display: block;
  position: absolute;
  right: 0;
  left: 0;
  height: calc(50% - 5px);
  border: 2px solid #06b6d4;          /* cyan border */
  transition: all 0.15s ease;
}

.download-cv-btn::before {
  top: 0;
  border-bottom-width: 0;
}

.download-cv-btn::after {
  bottom: 0;
  border-top-width: 0;
}

.download-cv-btn:active::before,
.download-cv-btn:active::after {
  right: 3px;
  left: 3px;
}

.download-cv-btn:active::before { top: 3px; }
.download-cv-btn:active::after  { bottom: 3px; }

.button_lg {
  position: relative;
  display: block;
  padding: 14px 28px;           /* bigger than original for better look */
  color: #fff;
  background-color: #0ea5e9;    /* sky-500 */
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(14, 165, 233, 0.3);
}

.button_sl {
  display: block;
  position: absolute;
  top: 0;
  bottom: -1px;
  left: -8px;
  width: 0;
  background-color: #f97316;    /* orange-500 */
  transform: skew(-15deg);
  transition: all 0.35s ease;
}

.button_text {
  position: relative;
  z-index: 1;
}

.download-cv-btn:hover .button_sl {
  width: calc(100% + 15px);
}

/* Keep your existing styles */
.delay-1000 { animation-delay: 1s; }
.slide-enter-active, .slide-leave-active { transition: all 0.35s ease; }
.slide-enter-from, .slide-leave-to { opacity: 0; transform: translateY(-20px); }
.line-clamp-3 { display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; }
/* ORBIT ANIMATION */
.orbit-container {
  position: absolute;
  width: 100%;
  height: 100%;
  animation: orbit 45s linear infinite;
}

.orbit-item {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotate(calc(var(--i) * 18deg)) translateX(190px) rotate(calc(var(--i) * -18deg));
}

.icon-wrapper {
  position: relative;
  transition: all 0.4s ease;
}

.tooltip {
  position: absolute;
  bottom: -36px;
  left: 50%;
  transform: translateX(-50%);
  background: rgba(0, 0, 0, 0.9);
  color: #06b6d4;
  padding: 6px 12px;
  border-radius: 8px;
  font-size: 13px;
  font-weight: 600;
  white-space: nowrap;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s ease;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
}

.icon-wrapper:hover .tooltip {
  opacity: 1;
}

@keyframes orbit {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.group:hover .orbit-container {
  animation-play-state: paused;
}
.typing-text {
  /* Ensures the gradient is applied correctly */
  display: inline-block;
}

/* Blinking cursor */
.cursor {
  display: inline-block;
  width: 3px;
  height: 1.1em;
  background: #67e8f9;
  margin-left: 4px;
  vertical-align: middle;
  animation: blink 0.8s infinite;
  box-shadow: 0 0 10px rgba(103, 232, 249, 0.8);
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}

/* Optional: make the cursor match the last letter's color a bit */
.bg-gradient-to-r span {
  background: inherit;
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}
/* Your existing button styles */
.download-cv-btn { /* unchanged - your beautiful button */ }
.download-cv-btn::before, .download-cv-btn::after { /* ... */ }
.button_lg { padding: 14px 28px; background-color: #0ea5e9; /* ... */ }
.button_sl { background-color: #f97316; /* ... */ }
.download-cv-btn:hover .button_sl { width: calc(100% + 15px); }

.delay-1000 { animation-delay: 1s; }
.slide-enter-active, .slide-leave-active { transition: all 0.35s ease; }
.slide-enter-from, .slide-leave-to { opacity: 0; transform: translateY(-20px); }
.line-clamp-3 { display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; }
</style>