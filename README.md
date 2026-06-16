# index.html
my personal website
```html
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Darren | University Application Portfolio</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            600: '#0284c7',
                            700: '#0369a1',
                            900: '#0c4a6e',
                        }
                    }
                }
            }
        }
    </script>
    <!-- Inter Font -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- Alpine.js for simple mobile menu interaction -->
    <script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .fade-in {
            animation: fadeIn 0.8s ease-out forwards;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(12px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="bg-gray-950 text-gray-100 antialiased selection:bg-brand-600 selection:text-white">

    <!-- Header / Navigation -->
    <header class="sticky top-0 z-50 bg-gray-950/80 backdrop-blur-md border-b border-gray-900">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <a href="#" class="text-xl font-bold tracking-tight text-white hover:text-brand-400 transition-colors">DARREN</a>
            <nav class="hidden md:flex space-x-8 text-sm font-medium text-gray-400">
                <a href="#about" class="hover:text-white transition-colors">About</a>
                <a href="#academics" class="hover:text-white transition-colors">Academics</a>
                <a href="#extracurriculars" class="hover:text-white transition-colors">Clubs & Sports</a>
                <a href="#project" class="hover:text-white transition-colors">Featured Project</a>
                <a href="#major" class="hover:text-white transition-colors">Intended Major</a>
            </nav>
            <!-- Mobile Menu Button -->
            <div class="md:hidden" x-data="{ open: false }">
                <button @click="open = !open" class="text-gray-400 hover:text-white focus:outline-none">
                    <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path x-show="!open" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                        <path x-show="open" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                    </svg>
                </button>
                <div x-show="open" @click.away="open = false" class="absolute top-16 left-0 w-full bg-gray-950 border-b border-gray-900 py-4 px-6 flex flex-col space-y-4 shadow-xl">
                    <a href="#about" @click="open = false" class="text-gray-300 hover:text-white">About</a>
                    <a href="#academics" @click="open = false" class="text-gray-300 hover:text-white">Academics</a>
                    <a href="#extracurriculars" @click="open = false" class="text-gray-300 hover:text-white">Clubs & Sports</a>
                    <a href="#project" @click="open = false" class="text-gray-300 hover:text-white">Featured Project</a>
                    <a href="#major" @click="open = false" class="text-gray-300 hover:text-white">Intended Major</a>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-16 space-y-24">

        <!-- 1. Hero Section -->
        <section class="fade-in flex flex-col-reverse md:flex-row items-center justify-between gap-12 pt-4">
            <div class="flex-1 space-y-6 text-center md:text-left">
                <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-brand-900/40 border border-brand-700/40 text-brand-400 text-xs font-semibold tracking-wide uppercase">
                    University Admissions Portfolio
                </div>
                <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight text-white">
                    Darren
                </h1>
                <p class="text-lg text-gray-400 max-w-xl leading-relaxed">
                    Grade 11 student combining high academic standards with mechanical problem-solving and an active dedication to physics, design, and physical endurance.
                </p>
                <div class="flex flex-wrap justify-center md:justify-start gap-4 pt-2">
                    <a href="#project" class="px-5 py-2.5 rounded-lg bg-brand-600 hover:bg-brand-700 text-white font-medium shadow-lg shadow-brand-600/20 transition-all">
                        Explore My Project
                    </a>
                    <a href="#academics" class="px-5 py-2.5 rounded-lg bg-gray-900 hover:bg-gray-800 text-gray-300 font-medium border border-gray-800 transition-all">
                        View Achievements
                    </a>
                </div>
            </div>
            <!-- Clean Placeholder Photo Area -->
            <div class="w-44 h-44 sm:w-56 sm:h-56 rounded-2xl bg-gradient-to-br from-brand-600 to-indigo-950 p-1 shadow-xl flex-shrink-0">
                <div class="w-full h-full bg-gray-900 rounded-[14px] flex items-center justify-center overflow-hidden">
                    <svg class="w-20 h-20 text-gray-700" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16 w-16v-2c0-2.66-5.33-4-8-4z"/>
                    </svg>
                </div>
            </div>
        </section>

        <!-- 2. About / Short Bio -->
        <section id="about" class="scroll-mt-24 bg-gray-900/40 border border-gray-900 rounded-2xl p-6 sm:p-8">
            <h2 class="text-xl sm:text-2xl font-bold text-white mb-4 flex items-center gap-2">
                <span class="w-1.5 h-6 bg-brand-600 rounded-full"></span> Biography
            </h2>
            <div class="text-gray-300 leading-relaxed space-y-4">
                <p class="text-lg text-white font-medium">Hi, I am Darren.</p>
                <p>
                    As an aspiring engineer, I find great joy in breaking down complex principles—whether they are rooted in the physical parameters of structure and material design, or the calculated frames of digital environments. My approach to learning emphasizes analytical discipline, creativity, and the relentless optimization of both mental and physical challenges.
                </p>
            </div>
        </section>

        <!-- 3. Academics & Awards -->
        <section id="academics" class="scroll-mt-24 space-y-6">
            <h2 class="text-xl sm:text-2xl font-bold text-white flex items-center gap-2">
                <span class="w-1.5 h-6 bg-brand-600 rounded-full"></span> Academic Foundations
            </h2>
            <div class="bg-gray-900/30 border border-gray-900 p-6 rounded-xl flex gap-5 items-start">
                <div class="p-3 bg-brand-950/50 rounded-lg text-brand-400 shrink-0 border border-brand-900">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M12 14l9-5-9-5-9 5 9 5z"></path>
                        <path stroke-linecap="round" stroke-linejoin="round" d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z"></path>
                    </svg>
                </div>
                <div class="space-y-2">
                    <div class="flex items-baseline gap-2">
                        <h3 class="text-lg font-bold text-white">IGCSE Certification Achievement</h3>
                        <span class="text-xs px-2 py-0.5 rounded bg-emerald-950 text-emerald-400 font-semibold border border-emerald-900">4 A* Grades</span>
                    </div>
                    <p class="text-sm text-gray-400 leading-relaxed">
                        Demonstrated exceptional academic mastery across foundational STEM disciplines. This rigorous background underpins my current higher-level analytics, preparation for rigorous standardizations, and long-term capability within an engineering honors framework.
                    </p>
                </div>
            </div>
        </section>

        <!-- 4. Extracurriculars (Clubs + Sports) -->
        <section id="extracurriculars" class="scroll-mt-24 space-y-6">
            <h2 class="text-xl sm:text-2xl font-bold text-white flex items-center gap-2">
                <span class="w-1.5 h-6 bg-brand-600 rounded-full"></span> Co-Curricular Involvement
            </h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <!-- Animation Club Card -->
                <div class="bg-gray-900/30 border border-gray-900 rounded-xl p-6 space-y-4">
                    <div class="flex justify-between items-start">
                        <div>
                            <h3 class="font-bold text-white text-lg">Animation Club</h3>
                            <p class="text-xs text-brand-400 font-medium">Digital Design & Collaboration</p>
                        </div>
                        <span class="text-[10px] uppercase font-bold text-gray-500 tracking-wider">Creative Focus</span>
                    </div>
                    <p class="text-sm text-gray-400 leading-relaxed">
                        Explored the intersections of geometric staging, structural pacing, and software manipulation. Collaborating with peers allowed me to appreciate user-centric UI aesthetics and fluid design elements.
                    </p>
                </div>
                <!-- Climbing Focus Card -->
                <div class="bg-gray-900/30 border border-gray-900 rounded-xl p-6 space-y-4">
                    <div class="flex justify-between items-start">
                        <div>
                            <h3 class="font-bold text-white text-lg">Sport Climbing</h3>
                            <p class="text-xs text-brand-400 font-medium">Athletic Commitment</p>
                        </div>
                        <span class="text-[10px] uppercase font-bold text-gray-500 tracking-wider">Athletic Focus</span>
                    </div>
                    <p class="text-sm text-gray-400 leading-relaxed">
                        Engaging in intensive physical training that sharpens personal endurance, situational split-second analysis, and tactical determination while executing high-altitude strategies.
                    </p>
                </div>
            </div>
        </section>

        <!-- 5. Key Project -->
        <section id="project" class="scroll-mt-24 space-y-6">
            <h2 class="text-xl sm:text-2xl font-bold text-white flex items-center gap-2">
                <span class="w-1.5 h-6 bg-brand-600 rounded-full"></span> Featured Accomplishment
            </h2>
            <div class="bg-gradient-to-b from-gray-900 via-gray-900 to-transparent border border-gray-900 rounded-2xl p-6 sm:p-8 space-y-6">
                <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2 border-b border-gray-800 pb-4">
                    <div>
                        <h3 class="text-xl font-bold text-white">Competitive Climbing Prize Winner</h3>
                        <p class="text-sm text-gray-400 mt-0.5">Project Type: Physical Systems & Biomechanics</p>
                    </div>
                    <span class="text-xs font-semibold px-3 py-1 rounded bg-brand-950 text-brand-400 border border-brand-900 self-start sm:self-auto">Award Distinction</span>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 text-sm">
                    <div class="space-y-1">
                        <h4 class="text-xs font-bold uppercase tracking-wider text-brand-400">The Scope</h4>
                        <p class="text-gray-300 leading-relaxed">
                            Applied analytical problem-solving directly onto physical routes, treating rock topography as structural obstacles that require careful force distribution.
                        </p>
                    </div>
                    <div class="space-y-1">
                        <h4 class="text-xs font-bold uppercase tracking-wider text-brand-400">Technical Skills</h4>
                        <p class="text-gray-300 leading-relaxed">
                            Calculated centers of gravity, load paths, friction vectors, and optimal kinetic energy conservation matrices to complete challenging routes efficiently.
                        </p>
                    </div>
                    <div class="space-y-1">
                        <h4 class="text-xs font-bold uppercase tracking-wider text-brand-400">The Impact</h4>
                        <p class="text-gray-300 leading-relaxed">
                            Achieved highly commended recognition and a formal prize placement, demonstrating structural spatial logic, calm decision-making, and high stress tolerance.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 6. Academic Interests / Intended Major -->
        <section id="major" class="scroll-mt-24 space-y-6">
            <h2 class="text-xl sm:text-2xl font-bold text-white flex items-center gap-2">
                <span class="w-1.5 h-6 bg-brand-600 rounded-full"></span> Future Aspirations
            </h2>
            <div class="bg-gray-900/20 border border-gray-900 rounded-xl p-6 sm:p-8 space-y-4">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-lg bg-brand-600/10 border border-brand-600/30 flex items-center justify-center text-brand-400">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"></path>
                            <path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"></path>
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-white">Intended Major: Engineering</h3>
                </div>
                <p class="text-gray-400 text-sm leading-relaxed max-w-3xl">
                    I aim to pursue an undergraduate program in Engineering where physical mechanics and design metrics overlap. My academic target is to deploy quantitative problem-solving frameworks onto practical research environments, building a bridge between theoretical mathematics and physical structural models.
                </p>
            </div>
        </section>

    </main>

    <!-- 7. Contact Footer -->
    <footer class="border-t border-gray-900 bg-gray-950 mt-16">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-8 flex flex-col sm:flex-row items-center justify-between gap-4 text-xs text-gray-500">
            <p>© 2026 Darren. Undergraduate Applicant Portfolio.</p>
            <div class="flex space-x-6">
                <span class="text-gray-400">Academic Portfolio Reference</span>
            </div>
        </div>
    </footer>

</body>
</html>

```
