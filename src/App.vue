<template>
<!-- Floating Particles -->
    <div id="particles" class="fixed inset-0 pointer-events-none z-0" aria-hidden="true">
        <div v-for="particle in particles" :key="particle.id" class="particle" :style="particle.style"></div>
    </div>

    <!-- Header / Navbar -->
    <header class="navbar" :class="{ scrolled: isScrolled }" role="banner">
        <nav class="max-w-7xl mx-auto flex items-center justify-between" role="navigation" aria-label="Main navigation">
            <!-- Logo -->
            <a @click="handleAnchorClick" href="#" class="flex items-center gap-2 group">
                <div class="w-10 h-10 rounded-lg  from-accent to-accentBlue flex items-center justify-center">
                    <img src="../asset/img/logo3.png" alt="Logo TD Digital" class="">
                </div>
                <span class="font-display font-bold text-xl text-white group-hover:text-accent transition-colors">TD
                    Digital</span>
            </a>

            <!-- Desktop Menu -->
            <div class="hidden lg:flex items-center gap-8">
                <a @click="handleAnchorClick" href="#beranda" class="text-gray-300 hover:text-accent transition-colors font-medium">Beranda</a>
                <a @click="handleAnchorClick" href="#layanan" class="text-gray-300 hover:text-accent transition-colors font-medium">Layanan</a>
                <a @click="handleAnchorClick" href="#produk" class="text-gray-300 hover:text-accent transition-colors font-medium">Produk</a>
                <a @click="handleAnchorClick" href="#portfolio" class="text-gray-300 hover:text-accent transition-colors font-medium">Portfolio</a>
                <a @click="handleAnchorClick" href="#testimoni" class="text-gray-300 hover:text-accent transition-colors font-medium">Testimoni</a>
                <a @click="handleAnchorClick" href="#tim" class="text-gray-300 hover:text-accent transition-colors font-medium">Tim Kami</a>
                <a @click="handleAnchorClick" href="#tentang" class="text-gray-300 hover:text-accent transition-colors font-medium">Tentang</a>
                <a @click="handleAnchorClick" href="https://www.hubapps.web.id" target="_blank" class="btn-primary px-6 py-2.5 rounded-lg font-semibold text-primary">HubApps</a>
            </div>

            <!-- Mobile Menu Button -->
            <button id="menuToggle" class="lg:hidden p-2 text-white" aria-label="Open menu" aria-controls="mobileMenu" :aria-expanded="mobileMenuOpen" @click="openMobileMenu">
                <Icon name="menu" class="w-6 h-6" />
            </button>
        </nav>
    </header>

    <!-- Mobile Menu -->
    <div v-if="mobileMenuOpen" class="mobile-menu-backdrop fixed inset-0 z-40 lg:hidden" aria-hidden="true" @click="closeMobileMenu"></div>
    <div id="mobileMenu" class="mobile-menu fixed inset-y-0 right-0 w-80 max-w-[85vw] overflow-y-auto bg-secondary z-50 p-8 lg:hidden" :class="{ active: mobileMenuOpen }" :aria-hidden="!mobileMenuOpen">
        <button id="menuClose" class="absolute top-6 right-6 p-2 text-white" aria-label="Close menu" @click="closeMobileMenu">
            <Icon name="x" class="w-6 h-6" />
        </button>
        <div class="flex flex-col gap-6 mt-16">
            <a @click="handleAnchorClick" href="#beranda" class="text-white hover:text-accent transition-colors font-medium text-lg">Beranda</a>
            <a @click="handleAnchorClick" href="#layanan" class="text-white hover:text-accent transition-colors font-medium text-lg">Layanan</a>
            <a @click="handleAnchorClick" href="#produk" class="text-white hover:text-accent transition-colors font-medium text-lg">Produk</a>
            <a @click="handleAnchorClick" href="#portfolio"
                class="text-white hover:text-accent transition-colors font-medium text-lg">Portfolio</a>
            <a @click="handleAnchorClick" href="#testimoni"
                class="text-white hover:text-accent transition-colors font-medium text-lg">Testimoni</a>
            <a @click="handleAnchorClick" href="#tim" class="text-white hover:text-accent transition-colors font-medium text-lg">Tim Kami</a>
            <a @click="handleAnchorClick" href="#tentang" class="text-white hover:text-accent transition-colors font-medium text-lg">Tentang</a>
            <a @click="handleAnchorClick" href="https://www.hubapps.web.id" target="_blank"
                class="btn-primary px-6 py-3 rounded-lg font-semibold text-primary text-center mt-4">HubApps</a>
        </div>
    </div>

    <!-- Hero Section -->
    <section id="beranda" class="relative min-h-screen flex items-center pt-20 overflow-hidden">
        <!-- Background Effects -->
        <div class="absolute inset-0 grid-pattern opacity-50"></div>
        <div class="gradient-orb w-96 h-96 bg-accent top-20 -left-48 float-anim"></div>
        <div class="gradient-orb w-80 h-80 bg-accentBlue bottom-20 right-0 float-anim" style="animation-delay: -4s;">
        </div>
        <div class="gradient-orb w-64 h-64 bg-purple-600 top-1/2 left-1/2 float-anim" style="animation-delay: -2s;">
        </div>

        <div class="max-w-7xl mx-auto px-6 py-20 relative z-10">
            <div class="grid lg:grid-cols-2 gap-12 items-center">
                <div class="space-y-8">
                    <div class="reveal">
                        <span
                            class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                            <Icon name="sparkles" class="w-4 h-4" />
                            Startup Teknologi Terpercaya
                        </span>
                    </div>

                    <h1
                        class="reveal reveal-delay-1 font-display text-4xl sm:text-5xl lg:text-6xl font-bold leading-tight">
                        Solusi Aplikasi <span
                            class="text-transparent bg-clip-text bg-gradient-to-r from-accent to-accentBlue">Digital</span>
                        untuk Sekolah, Instansi, dan Bisnis
                    </h1>

                    <p class="reveal reveal-delay-2 text-gray-400 text-lg max-w-xl">
                        Kami mengembangkan aplikasi digital inovatif yang membantu transformasi digital institusi
                        pendidikan, pemerintahan, dan bisnis dengan teknologi terkini.
                    </p>

                    <div class="reveal reveal-delay-3 flex flex-wrap gap-4">
                        <a @click="handleAnchorClick" href="#video-section"
                            class="btn-primary px-8 py-4 rounded-xl font-semibold text-primary flex items-center gap-2">
                            <Icon name="play-circle" class="w-5 h-5" />
                            Lihat Demo
                        </a>
                        <a id="videoBtn" href="https://www.youtube.com/@tddigitalofficial" target="_blank" 
                            class="btn-secondary px-8 py-4 rounded-xl font-semibold text-white flex items-center gap-2">
                            <Icon name="video" class="w-5 h-5" />
                            Video Youtube
                        </a>
                    </div>

                    <div class="reveal reveal-delay-4 flex items-center gap-8 pt-4">
                        <div class="text-center">
                            <div class="font-display text-3xl font-bold text-accent">150+</div>
                            <div class="text-gray-500 text-sm">Klien Puas</div>
                        </div>
                        <div class="w-px h-12 bg-border"></div>
                        <div class="text-center">
                            <div class="font-display text-3xl font-bold text-accent">50+</div>
                            <div class="text-gray-500 text-sm">Proyek Sukses</div>
                        </div>
                        <div class="w-px h-12 bg-border"></div>
                        <div class="text-center">
                            <div class="font-display text-3xl font-bold text-accent">5+</div>
                            <div class="text-gray-500 text-sm">Tahun Pengalaman</div>
                        </div>
                    </div>
                </div>

                <div class="reveal reveal-delay-2 relative hidden lg:block">
                    <div class="relative">
                        <!-- 3D-like Dashboard Preview -->
                        <div
                            class="bg-card rounded-2xl border border-border p-4 shadow-2xl transform rotate-3 hover:rotate-0 transition-transform duration-500">
                            <div class="flex items-center gap-2 mb-4">
                                <div class="w-3 h-3 rounded-full bg-red-500"></div>
                                <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
                                <div class="w-3 h-3 rounded-full bg-green-500"></div>
                            </div>
                            <div class="bg-secondary rounded-lg p-6 space-y-4">
                                <div class="flex items-center justify-between">
                                    <div class="h-4 w-32 bg-border rounded"></div>
                                    <div class="h-8 w-24 bg-accent/20 rounded"></div>
                                </div>
                                <div class="grid grid-cols-3 gap-4">
                                    <div class="bg-card p-4 rounded-lg">
                                        <div class="h-8 w-8 bg-accent/20 rounded-lg mb-2"></div>
                                        <div class="h-3 w-16 bg-border rounded"></div>
                                    </div>
                                    <div class="bg-card p-4 rounded-lg">
                                        <div class="h-8 w-8 bg-accentBlue/20 rounded-lg mb-2"></div>
                                        <div class="h-3 w-16 bg-border rounded"></div>
                                    </div>
                                    <div class="bg-card p-4 rounded-lg">
                                        <div class="h-8 w-8 bg-purple-500/20 rounded-lg mb-2"></div>
                                        <div class="h-3 w-16 bg-border rounded"></div>
                                    </div>
                                </div>
                                <div class="h-32 bg-gradient-to-r from-accent/10 to-accentBlue/10 rounded-lg"></div>
                            </div>
                        </div>

                        <!-- Floating Elements -->
                        <div
                            class="absolute -top-8 -right-8 bg-card rounded-xl border border-border p-4 shadow-xl float-anim">
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-full bg-accent/20 flex items-center justify-center">
                                    <Icon name="check-circle" class="w-5 h-5 text-accent" />
                                </div>
                                <div>
                                    <div class="text-sm font-semibold">Terpercaya</div>
                                    <div class="text-xs text-gray-500">100% aman</div>
                                </div>
                            </div>
                        </div>

                        <div class="absolute -bottom-4 -left-8 bg-card rounded-xl border border-border p-4 shadow-xl float-anim"
                            style="animation-delay: -3s;">
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-full bg-accentBlue/20 flex items-center justify-center">
                                    <Icon name="users" class="w-5 h-5 text-accentBlue" />
                                </div>
                                <div>
                                    <div class="text-sm font-semibold">Setia Menemani</div>
                                    <div class="text-xs text-gray-500">24 Online</div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Scroll Indicator -->
        <div class="absolute bottom-8 left-1/2 -translate-x-1/2 animate-bounce">
            <Icon name="chevron-down" class="w-6 h-6 text-accent" />
        </div>
    </section>

    <!-- Services Section -->
    <section id="layanan" class="py-24 relative">
        <div class="gradient-orb w-72 h-72 bg-accentBlue/30 top-0 right-0"></div>

        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <span
                    class="reveal inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                    <Icon name="briefcase" class="w-4 h-4" />
                    Layanan Kami
                </span>
                <h2 class="reveal reveal-delay-1 font-display text-3xl sm:text-4xl lg:text-5xl font-bold mb-6">
                    Solusi Digital <span class="text-accent">Lengkap</span>
                </h2>
                <p class="reveal reveal-delay-2 text-gray-400 max-w-2xl mx-auto">
                    Kami menyediakan berbagai layanan pengembangan aplikasi untuk memenuhi kebutuhan digital Anda
                </p>
            </div>

            <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Service 1 -->
                <article class="reveal service-card rounded-2xl p-6 group">
                    <div
                        class="w-14 h-14 rounded-xl bg-accent/10 flex items-center justify-center mb-6 group-hover:bg-accent/20 transition-colors">
                        <Icon name="fingerprint" class="w-7 h-7 text-accent" />
                    </div>
                    <h3 class="font-display text-xl font-semibold mb-3">Web Application Development</h3>
                    <p class="text-gray-400 mb-6">Pengembangan aplikasi web modern dan responsif sesuai kebutuhan bisnis dengan performa optimal, aman, dan mudah dikembangkan.</p>
                    <!--<div class="flex gap-3">
                        <a @click="handleAnchorClick" href="#"
                            class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                            <Icon name="eye" class="w-4 h-4" />
                            Demo
                        </a>
                        <a href="https://oam.tddig.my.id/" target="_blank"
                            class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                            Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                        </a>
                    </div>-->
                </article>

                <!-- Service 2 -->
                <article class="reveal reveal-delay-1 service-card rounded-2xl p-6 group">
                    <div
                        class="w-14 h-14 rounded-xl bg-accentBlue/10 flex items-center justify-center mb-6 group-hover:bg-accentBlue/20 transition-colors">
                        <Icon name="vote" class="w-7 h-7 text-accentBlue" />
                    </div>
                    <h3 class="font-display text-xl font-semibold mb-3">Android Application Development</h3>
                    <p class="text-gray-400 mb-6">Pengembangan aplikasi Android native sesuai kebutuhan bisnis Anda dengan performa optimal dan UI/UX modern.</p>
                    <!--<div class="flex gap-3">
                        <a @click="handleAnchorClick" href="#"
                            class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                            <Icon name="eye" class="w-4 h-4" />
                            Demo
                        </a>
                        <a href="https://evoting.tddig.my.id/" target="_blank"
                            class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                            Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                        </a>
                    </div>-->
                </article>

                <!-- Service 3 -->
                <article class="reveal reveal-delay-2 service-card rounded-2xl p-6 group">
                    <div
                        class="w-14 h-14 rounded-xl bg-purple-500/10 flex items-center justify-center mb-6 group-hover:bg-purple-500/20 transition-colors">
                        <Icon name="school" class="w-7 h-7 text-purple-500" />
                    </div>
                    <h3 class="font-display text-xl font-semibold mb-3">Website Development</h3>
                    <p class="text-gray-400 mb-6">Pembuatan website profesional, responsif, dan modern untuk meningkatkan kehadiran digital bisnis, organisasi, maupun personal.</p>
                    <!--<div class="flex gap-3">
                        <a href="https://youtu.be/t18ybc6enbQ" target="_blank"
                            class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                            <Icon name="eye" class="w-4 h-4" />
                            Demo
                        </a>
                        <a href="https://eosis.tddig.my.id/" target="_blank"
                            class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                            Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                        </a>
                    </div>-->
                </article>

                <!-- Service 4 -->
                <article class="reveal reveal-delay-3 service-card rounded-2xl p-6 group">
                    <div
                        class="w-14 h-14 rounded-xl bg-orange-500/10 flex items-center justify-center mb-6 group-hover:bg-orange-500/20 transition-colors">
                        <Icon name="globe" class="w-7 h-7 text-orange-500" />
                    </div>
                    <h3 class="font-display text-xl font-semibold mb-3">Custom Software</h3>
                    <p class="text-gray-400 mb-6">Pengembangan software khusus yang dirancang sesuai alur kerja dan kebutuhan bisnis untuk meningkatkan efisiensi dan produktivitas.</p>
                    <!--<div class="flex gap-3">
                        <a @click="handleAnchorClick" href="#"
                            class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                            <Icon name="eye" class="w-4 h-4" />
                            Demo
                        </a>
                        <a @click="handleAnchorClick" href="#"
                            class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                            Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                        </a>
                    </div>-->
                </article>

                <!-- Service 5 -->
                <article class="reveal reveal-delay-4 service-card rounded-2xl p-6 group">
                    <div
                        class="w-14 h-14 rounded-xl bg-pink-500/10 flex items-center justify-center mb-6 group-hover:bg-pink-500/20 transition-colors">
                        <Icon name="smartphone" class="w-7 h-7 text-pink-500" />
                    </div>
                    <h3 class="font-display text-xl font-semibold mb-3">UI/UX Design</h3>
                    <p class="text-gray-400 mb-6">Perancangan UI/UX yang modern, intuitif, dan berorientasi pada pengguna untuk menciptakan pengalaman digital yang nyaman dan efektif.</p>
                    <!---<div class="flex gap-3">
                        <a @click="handleAnchorClick" href="#"
                            class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                            <Icon name="eye" class="w-4 h-4" />
                            Demo
                        </a>
                        <a @click="handleAnchorClick" href="#"
                            class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                            Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                        </a>
                    </div>-->
                </article>

                <!-- Service 6 -->
                <article class="reveal reveal-delay-5 service-card rounded-2xl p-6 group">
                    <div
                        class="w-14 h-14 rounded-xl bg-cyan-500/10 flex items-center justify-center mb-6 group-hover:bg-cyan-500/20 transition-colors">
                        <Icon name="code-2" class="w-7 h-7 text-cyan-500" />
                    </div>
                    <h3 class="font-display text-xl font-semibold mb-3">Maintenance & Support</h3>
                    <p class="text-gray-400 mb-6">Pemeliharaan dan dukungan teknis berkelanjutan untuk menjaga aplikasi tetap aman, stabil, optimal, dan dapat diandalkan.</p>
                    <!--<div class="flex gap-3">
                        <a @click="handleAnchorClick" href="#"
                            class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                            <Icon name="eye" class="w-4 h-4" />
                            Demo
                        </a>
                        <a @click="handleAnchorClick" href="#"
                            class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                            Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                        </a>
                    </div>-->
                </article>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="produk" class="py-24 relative bg-secondary/50">
        <div class="gradient-orb w-72 h-72 bg-accent/20 bottom-0 left-0"></div>

        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <span
                    class="reveal inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                    <Icon name="shopping-bag" class="w-4 h-4" />
                    Produk Kami
                </span>
                <h2 class="reveal reveal-delay-1 font-display text-3xl sm:text-4xl lg:text-5xl font-bold mb-6">
                    Produk <span class="text-accent">Siap Digunakan</span>
                </h2>
                <p class="reveal reveal-delay-2 text-gray-400 max-w-2xl mx-auto">
                    Pilih solusi digital yang dirancang untuk membantu operasional sekolah, instansi, dan bisnis Anda.
                </p>
            </div>

            <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
                <article class="reveal group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div class="aspect-video bg-gradient-to-br from-accent/20 to-accentBlue/20">
                            <img src="../asset/img/absensi.png" alt="Tampilan produk OAM" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105">
                        </div>
                        <div class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
                    </div>
                    <div class="mt-5">
                        <h3 class="font-display text-xl font-semibold mb-2">OAM - Online Attendance Management</h3>
                        <p class="text-gray-400 text-sm mb-5">Aplikasi absensi siswa modern yang membantu guru memantau kehadiran secara praktis dan terstruktur.</p>
                        <div class="flex flex-wrap gap-3">
                            <a href="https://youtu.be/K16R3t1njgQ" target="_blank" rel="noopener noreferrer"
                                class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                                <Icon name="eye" class="w-4 h-4" />
                                Demo
                            </a>
                            <a href="https://www.hubapps.web.id/" target="_blank" rel="noopener noreferrer"
                                class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                                Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                            </a>
                        </div>
                    </div>
                </article>

                <article class="reveal reveal-delay-1 group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div class="aspect-video bg-gradient-to-br from-purple-500/20 to-pink-500/20">
                            <img src="../asset/img/evot.png" alt="Tampilan produk E-Voting" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105">
                        </div>
                        <div class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
                    </div>
                    <div class="mt-5">
                        <h3 class="font-display text-xl font-semibold mb-2">E-Voting Sekolah</h3>
                        <p class="text-gray-400 text-sm mb-5">Platform pemilihan digital yang aman, transparan, dan realtime untuk berbagai kebutuhan organisasi.</p>
                        <div class="flex flex-wrap gap-3">
                            <a href="https://youtu.be/xV2M2p_1Ylk" target="_blank" rel="noopener noreferrer"
                                class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                                <Icon name="eye" class="w-4 h-4" />
                                Demo
                            </a>
                            <a href="https://www.hubapps.web.id/" target="_blank" rel="noopener noreferrer"
                                class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                                Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                            </a>
                        </div>
                    </div>
                </article>

                <article class="reveal reveal-delay-2 group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div class="aspect-video bg-gradient-to-br from-orange-500/20 to-red-500/20">
                            <img src="../asset/img/eosis.jpg" alt="Tampilan produk E-OSIS" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105">
                        </div>
                        <div class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
                    </div>
                    <div class="mt-5">
                        <h3 class="font-display text-xl font-semibold mb-2">E-OSIS</h3>
                        <p class="text-gray-400 text-sm mb-5">Solusi digital pemilihan ketua dan wakil ketua OSIS yang mudah, cepat, dan dapat dipantau realtime.</p>
                        <div class="flex flex-wrap gap-3">
                            <a href="https://youtu.be/t18ybc6enbQ" target="_blank" rel="noopener noreferrer"
                                class="btn-secondary px-4 py-2 rounded-lg text-sm text-white flex items-center gap-2">
                                <Icon name="eye" class="w-4 h-4" />
                                Demo
                            </a>
                            <a href="https://www.hubapps.web.id/" target="_blank" rel="noopener noreferrer"
                                class="text-accent hover:text-accentLight transition-colors text-sm font-medium flex items-center gap-1">
                                Kunjungi <Icon name="arrow-right" class="w-4 h-4" />
                            </a>
                        </div>
                    </div>
                </article>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="py-24 relative">
        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <span
                    class="reveal inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                    <Icon name="folder-open" class="w-4 h-4" />
                    Portfolio Kami
                </span>
                <h2 class="reveal reveal-delay-1 font-display text-3xl sm:text-4xl lg:text-5xl font-bold mb-6">
                    Aplikasi <span class="text-accent">Open</span> Source
                </h2>
                <p class="reveal reveal-delay-2 text-gray-400 max-w-2xl mx-auto">
                    Beberapa projek aplikasi gratis yang dapat di download open source
                </p>
            </div>

            <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Portfolio 1 -->
                <article class="reveal group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div
                            class="aspect-video bg-gradient-to-br from-accent/20 to-accentBlue/20 flex items-center justify-center">
                            <img src="../asset/img/bukuhub.png">
                        </div>
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                        </div>
                        <div
                            class="absolute bottom-0 left-0 right-0 p-6 translate-y-full group-hover:translate-y-0 transition-transform duration-300">
                            <a href="https://github.com/ikhsan3adi/sistem-perpustakaan-qr-code?tab=readme-ov-file"
                                target="_blank"
                                class="btn-primary w-full py-3 rounded-lg font-semibold text-primary text-center block">
                                Lihat Detail
                            </a>
                        </div>
                    </div>
                    <div class="mt-4">
                        <h3 class="font-display text-lg font-semibold mb-2">E-Perpustakaan</h3>
                        <p class="text-gray-400 text-sm">E perpustakaan atau perpustakaan digital adalah tempat di mana
                            Anda dapat meminjam koleksi buku dan sumber edukatif lainnya secara digital dan sederhanan
                        </p>
                    </div>
                </article>

                <!-- Portfolio 2 -->
                <article class="reveal reveal-delay-1 group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div
                            class="aspect-video bg-gradient-to-br from-purple-500/20 to-pink-500/20 flex items-center justify-center">
                            <img src="../asset/img/opresent.png">
                        </div>
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                        </div>
                        <div
                            class="absolute bottom-0 left-0 right-0 p-6 translate-y-full group-hover:translate-y-0 transition-transform duration-300">
                            <a href="https://josephines1.github.io/o-present-landing-page/" target="_blank"
                                class="btn-primary w-full py-3 rounded-lg font-semibold text-primary text-center block">
                                Lihat Detail
                            </a>
                        </div>
                    </div>
                    <div class="mt-4">
                        <h3 class="font-display text-lg font-semibold mb-2">O-Present Pegawai</h3>
                        <p class="text-gray-400 text-sm">O-Present adalah aplikasi berbasis web yang dirancang untuk
                            mencatat kehadiran secara online dengan mudah dan efisien GPS Real-time dan Foto Selfie.
                        </p>
                    </div>
                </article>

                <!-- Portfolio 3 -->
                <article class="reveal reveal-delay-2 group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div
                            class="aspect-video bg-gradient-to-br from-orange-500/20 to-red-500/20 flex items-center justify-center">
                            <img src="../asset/img/absenqr.png">
                        </div>
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                        </div>
                        <div
                            class="absolute bottom-0 left-0 right-0 p-6 translate-y-full group-hover:translate-y-0 transition-transform duration-300">
                            <a href="https://github.com/ikhsan3adi/absensi-sekolah-qr-code?tab=readme-ov-file"
                                target="_blank"
                                class="btn-primary w-full py-3 rounded-lg font-semibold text-primary text-center block">
                                Lihat Detail
                            </a>
                        </div>
                    </div>
                    <div class="mt-4">
                        <h3 class="font-display text-lg font-semibold mb-2">Absensi Sekolah QR Code</h3>
                        <p class="text-gray-400 text-sm">Sistem absensi siswa dan guru/pegawai masuk dan pulang dengan
                            metode atau menggunakan sistem scan barcode atau bisa FRID.</p>
                    </div>
                </article>

                <!-- Portfolio 4 -->
                <article class="reveal reveal-delay-3 group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div
                            class="aspect-video bg-gradient-to-br from-cyan-500/20 to-blue-500/20 flex items-center justify-center">
                            <div class="w-3/4 h-3/4 bg-secondary rounded-lg shadow-xl flex items-center justify-center">
                                <Icon name="shopping-bag" class="w-16 h-16 text-cyan-500/50" />
                            </div>
                        </div>
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                        </div>
                        <div
                            class="absolute bottom-0 left-0 right-0 p-6 translate-y-full group-hover:translate-y-0 transition-transform duration-300">
                            <a @click="handleAnchorClick" href="#"
                                class="btn-primary w-full py-3 rounded-lg font-semibold text-primary text-center block">
                                Lihat Detail
                            </a>
                        </div>
                    </div>
                    <div class="mt-4">
                        <h3 class="font-display text-lg font-semibold mb-2">E-Commerce Batik Nusantara</h3>
                        <p class="text-gray-400 text-sm">Marketplace produk batik dengan fitur multi-vendor dan payment
                            gateway terintegrasi.</p>
                    </div>
                </article>

                <!-- Portfolio 5 -->
                <article class="reveal reveal-delay-4 group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div
                            class="aspect-video bg-gradient-to-br from-green-500/20 to-teal-500/20 flex items-center justify-center">
                            <div class="w-3/4 h-3/4 bg-secondary rounded-lg shadow-xl flex items-center justify-center">
                                <Icon name="heart-pulse" class="w-16 h-16 text-green-500/50" />
                            </div>
                        </div>
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                        </div>
                        <div
                            class="absolute bottom-0 left-0 right-0 p-6 translate-y-full group-hover:translate-y-0 transition-transform duration-300">
                            <a @click="handleAnchorClick" href="#"
                                class="btn-primary w-full py-3 rounded-lg font-semibold text-primary text-center block">
                                Lihat Detail
                            </a>
                        </div>
                    </div>
                    <div class="mt-4">
                        <h3 class="font-display text-lg font-semibold mb-2">SIMRS Rumah Sakit</h3>
                        <p class="text-gray-400 text-sm">Sistem informasi manajemen rumah sakit dengan fitur rekam medis
                            dan antrian online.</p>
                    </div>
                </article>

                <!-- Portfolio 6 -->
                <article class="reveal reveal-delay-5 group">
                    <div class="relative overflow-hidden rounded-2xl bg-card border border-border">
                        <div
                            class="aspect-video bg-gradient-to-br from-yellow-500/20 to-amber-500/20 flex items-center justify-center">
                            <div class="w-3/4 h-3/4 bg-secondary rounded-lg shadow-xl flex items-center justify-center">
                                <Icon name="landmark" class="w-16 h-16 text-yellow-500/50" />
                            </div>
                        </div>
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-primary via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                        </div>
                        <div
                            class="absolute bottom-0 left-0 right-0 p-6 translate-y-full group-hover:translate-y-0 transition-transform duration-300">
                            <a @click="handleAnchorClick" href="#"
                                class="btn-primary w-full py-3 rounded-lg font-semibold text-primary text-center block">
                                Lihat Detail
                            </a>
                        </div>
                    </div>
                    <div class="mt-4">
                        <h3 class="font-display text-lg font-semibold mb-2">Portal Pelayanan Publik</h3>
                        <p class="text-gray-400 text-sm">Website pelayanan publik dengan sistem pengaduan online dan
                            tracking status pengajuan.</p>
                    </div>
                </article>
            </div>
        </div>
    </section>

    <!-- Video Demo Section -->
    <section id="video-section" class="py-24 relative bg-secondary/50">
        <div class="gradient-orb w-96 h-96 bg-accent/30 -left-48 top-1/2 -translate-y-1/2"></div>

        <div class="max-w-5xl mx-auto px-6">
            <div class="text-center mb-16">
                <span
                    class="reveal inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                    <Icon name="video" class="w-4 h-4" />
                    Video Demo
                </span>
                <h2 class="reveal reveal-delay-1 font-display text-3xl sm:text-4xl lg:text-5xl font-bold mb-6">
                    Lihat Cara Kerja <span class="text-accent">Aplikasi</span> Kami
                </h2>
            </div>

            <div
                class="reveal reveal-delay-2 relative aspect-video bg-card rounded-2xl border border-border overflow-hidden group">
                <div
                    class="absolute inset-0 bg-gradient-to-br from-accent/10 to-accentBlue/10 flex items-center justify-center">
                    <button id="playvideoBtn" @click="openVideoModal"
                        class="w-20 h-20 rounded-full bg-accent flex items-center justify-center group-hover:scale-110 transition-transform pulse-glow"
                        aria-label="Play video">
                        <Icon name="play" class="w-8 h-8 text-primary ml-1" />
                    </button>
                </div>
                <div class="absolute bottom-4 left-4 right-4 flex items-center justify-between text-sm text-gray-400">
                    <span>TD Digital @2026</span>
                    <span>3:45</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimoni" class="py-24 relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <span
                    class="reveal inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                    <Icon name="message-circle" class="w-4 h-4" />
                    Testimoni
                </span>
                <h2 class="reveal reveal-delay-1 font-display text-3xl sm:text-4xl lg:text-5xl font-bold mb-6">
                    Apa Kata <span class="text-accent">Klien</span> Kami
                </h2>
                <p class="reveal reveal-delay-2 text-gray-400 max-w-2xl mx-auto">
                    Kepuasan klien adalah prioritas utama kami
                </p>
            </div>

            <div class="reveal reveal-delay-2 relative">
                <div id="testimonialSlider" class="testimonial-slider" @mouseenter="pauseAutoplay" @mouseleave="resumeAutoplay">
                    <div id="testimonialTrack" class="testimonial-track" :style="{ transform: `translateX(-${currentSlide * (100 / slidesPerView)}%)` }">
                        <!-- Testimonial 1 -->
                        <div class="testimonial-card p-4">
                            <div class="bg-card rounded-2xl p-6 border border-border h-full">
                                <div class="flex items-center gap-1 mb-4">
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                </div>
                                <p class="text-gray-300 mb-6">"E voting, berjalan lancar tanpa kendala, mudah
                                    dioperasikan, dan rekap suara sesuai harapan. Sukses selalu buat pengembang."</p>
                                <div class="flex items-center gap-4">
                                    <div
                                        class="w-12 h-12 rounded-full bg-gradient-to-br from-accent to-accentBlue flex items-center justify-center font-semibold text-primary">
                                        AS</div>
                                    <div>
                                        <div class="font-semibold">Agus Salimsyam</div>
                                        <div class="text-gray-500 text-sm">SMKN6 Palopo</div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Testimonial 2 -->
                        <div class="testimonial-card p-4">
                            <div class="bg-card rounded-2xl p-6 border border-border h-full">
                                <div class="flex items-center gap-1 mb-4">
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                </div>
                                <p class="text-gray-300 mb-6">"Aplikasi e-votingnya benar-benar membantu! Cepat, aman,
                                    dan hasilnya akurat. Sangat direkomendasikan."</p>
                                <div class="flex items-center gap-4">
                                    <div
                                        class="w-12 h-12 rounded-full bg-gradient-to-br from-purple-500 to-pink-500 flex items-center justify-center font-semibold text-white">
                                        FR</div>
                                    <div>
                                        <div class="font-semibold">Fachrudin</div>
                                        <div class="text-gray-500 text-sm">SMA IT Al Qudwah</div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Testimonial 3 -->
                        <div class="testimonial-card p-4">
                            <div class="bg-card rounded-2xl p-6 border border-border h-full">
                                <div class="flex items-center gap-1 mb-4">
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                </div>
                                <p class="text-gray-300 mb-6">"Website company profile yang dibuat sangat profesional.
                                    Desain modern dan loading cepat. Highly recommended!"</p>
                                <div class="flex items-center gap-4">
                                    <div
                                        class="w-12 h-12 rounded-full bg-gradient-to-br from-orange-500 to-red-500 flex items-center justify-center font-semibold text-white">
                                        AP</div>
                                    <div>
                                        <div class="font-semibold">Ahmad Pratama</div>
                                        <div class="text-gray-500 text-sm">CEO, PT Maju Bersama</div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Testimonial 4 -->
                        <div class="testimonial-card p-4">
                            <div class="bg-card rounded-2xl p-6 border border-border h-full">
                                <div class="flex items-center gap-1 mb-4">
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                </div>
                                <p class="text-gray-300 mb-6">"Aplikasi absensi digital membantu efisiensi manajemen
                                    kehadiran 500+ pegawai kami. Laporan real-time sangat membantu."</p>
                                <div class="flex items-center gap-4">
                                    <div
                                        class="w-12 h-12 rounded-full bg-gradient-to-br from-cyan-500 to-blue-500 flex items-center justify-center font-semibold text-white">
                                        BS</div>
                                    <div>
                                        <div class="font-semibold">Budi Santoso</div>
                                        <div class="text-gray-500 text-sm">Kepala Dinas, Dinas Pendidikan</div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Testimonial 5 -->
                        <div class="testimonial-card p-4">
                            <div class="bg-card rounded-2xl p-6 border border-border h-full">
                                <div class="flex items-center gap-1 mb-4">
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                    <Icon name="star" class="w-5 h-5 text-yellow-500 fill-yellow-500" />
                                </div>
                                <p class="text-gray-300 mb-6">"Tim DigiNusa sangat profesional dan komunikatif. Proses
                                    development berjalan lancar sesuai timeline yang disepakati."</p>
                                <div class="flex items-center gap-4">
                                    <div
                                        class="w-12 h-12 rounded-full bg-gradient-to-br from-green-500 to-teal-500 flex items-center justify-center font-semibold text-white">
                                        LN</div>
                                    <div>
                                        <div class="font-semibold">Linda Nugraha</div>
                                        <div class="text-gray-500 text-sm">IT Manager, Bank Daerah</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Slider Controls -->
                <div class="flex items-center justify-center gap-4 mt-8">
                    <button id="prevTestimonial" @click="previousSlide"
                        class="w-12 h-12 rounded-full border border-border flex items-center justify-center text-white hover:border-accent hover:text-accent transition-colors"
                        aria-label="Previous testimonial">
                        <Icon name="chevron-left" class="w-5 h-5" />
                    </button>
                    <div id="testimonialDots" class="flex gap-2">
                        <button v-for="(_, index) in dotCount" :key="index" @click="goToSlide(index)"
                            :class="index === currentSlide ? 'w-6 bg-accent' : 'bg-border hover:bg-accent/50'"
                            class="w-2 h-2 rounded-full transition-all" :aria-label="`Go to slide ${index + 1}`"></button>
                    </div>
                    <button id="nextTestimonial" @click="nextSlide"
                        class="w-12 h-12 rounded-full border border-border flex items-center justify-center text-white hover:border-accent hover:text-accent transition-colors"
                        aria-label="Next testimonial">
                        <Icon name="chevron-right" class="w-5 h-5" />
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Team Section -->
    <section id="tim" class="py-24 relative bg-secondary/50">

        <div class="max-w-7xl mx-auto px-6">

            <!-- Heading -->
            <div class="text-center mb-16">
                <span
                    class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                    <Icon name="users" class="w-4 h-4" />
                    Tim Kami
                </span>

                <h2 class="font-display text-3xl sm:text-4xl lg:text-5xl font-bold mb-6">
                    Kenalan dengan <span class="text-accent">Tim</span> Kami
                </h2>

                <p class="text-gray-400 max-w-2xl mx-auto">
                    Profesional berpengalaman yang siap membantu transformasi digital Anda
                </p>
            </div>

            <!-- Team Grid -->
            <div class="grid sm:grid-cols-2 gap-10 max-w-4xl mx-auto">

                <!-- Team 1 -->
                <article class="group">
                    <div
                        class="relative overflow-hidden rounded-2xl bg-card border border-border p-8 text-center transition duration-300 hover:-translate-y-2 hover:shadow-xl">

                        <!-- Foto -->
                        <div
                            class="w-24 h-24 mx-auto rounded-full bg-gradient-to-br from-accent to-accentBlue flex items-center justify-center mb-5 group-hover:scale-110 transition">
                            <span class="text-3xl font-bold text-primary">RL</span>
                        </div>

                        <!-- Nama -->
                        <h3 class="font-display text-lg font-semibold mb-1">
                            Ramlan
                        </h3>

                        <!-- Jabatan -->
                        <p class="text-accent text-sm mb-4">
                            CEO & Founder
                        </p>

                        <!-- Deskripsi -->
                        <p class="text-gray-500 text-sm mb-5">
                            Berpengalaman 10+ tahun di bidang teknologi serta manajemen startup.
                        </p>

                        <!-- Social -->
                        <div class="flex justify-center gap-3">
                            <a @click="handleAnchorClick" href="#"
                                class="w-8 h-8 rounded-full bg-secondary flex items-center justify-center text-gray-400 hover:text-accent hover:bg-accent/10 transition">
                                <Icon name="linkedin" class="w-4 h-4" />
                            </a>

                            <a @click="handleAnchorClick" href="#"
                                class="w-8 h-8 rounded-full bg-secondary flex items-center justify-center text-gray-400 hover:text-accent hover:bg-accent/10 transition">
                                <Icon name="twitter" class="w-4 h-4" />
                            </a>
                        </div>

                    </div>
                </article>

                <!-- Team 2 -->
                <article class="group">
                    <div
                        class="relative overflow-hidden rounded-2xl bg-card border border-border p-8 text-center transition duration-300 hover:-translate-y-2 hover:shadow-xl">

                        <!-- Foto -->
                        <div
                            class="w-24 h-24 mx-auto rounded-full bg-gradient-to-br from-purple-500 to-pink-500 flex items-center justify-center mb-5 group-hover:scale-110 transition">
                            <img src="../asset/img/ichal.jpg" alt="Ichal" class="w-full h-full object-cover rounded-full" /> 
                        </div>

                        <!-- Nama -->
                        <h3 class="font-display text-lg font-semibold mb-1">
                            Ichal
                        </h3>

                        <!-- Jabatan -->
                        <p class="text-purple-400 text-sm mb-4">
                            Team 1
                        </p>

                        <!-- Deskripsi -->
                        <p class="text-gray-500 text-sm mb-5">
                            Full-stack developer dengan pengalaman membangun sistem
                            informasi digital maupun desain.
                        </p>

                        <!-- Social -->
                        <div class="flex justify-center gap-3">
                            <a @click="handleAnchorClick" href="#"
                                class="w-8 h-8 rounded-full bg-secondary flex items-center justify-center text-gray-400 hover:text-purple-400 hover:bg-purple-400/10 transition">
                                <Icon name="linkedin" class="w-4 h-4" />
                            </a>

                            <a @click="handleAnchorClick" href="#"
                                class="w-8 h-8 rounded-full bg-secondary flex items-center justify-center text-gray-400 hover:text-purple-400 hover:bg-purple-400/10 transition">
                                <Icon name="github" class="w-4 h-4" />
                            </a>
                        </div>

                    </div>
                </article>

            </div>

        </div>
    </section>

    <!-- About Section -->
    <section id="tentang" class="py-24 relative">
        <div class="max-w-7xl mx-auto px-6">
            <div class="grid lg:grid-cols-2 gap-16 items-center">
                <div class="reveal order-2 lg:order-1">
                    <div class="relative">
                        <div class="bg-card rounded-2xl border border-border p-8 relative z-10">
                            <div class="grid grid-cols-2 gap-6">
                                <div class="bg-secondary rounded-xl p-6 text-center">
                                    <div class="font-display text-4xl font-bold text-accent mb-2">150+</div>
                                    <div class="text-gray-400">Klien Aktif</div>
                                </div>
                                <div class="bg-secondary rounded-xl p-6 text-center">
                                    <div class="font-display text-4xl font-bold text-accentBlue mb-2">50+</div>
                                    <div class="text-gray-400">Proyek Sukses</div>
                                </div>
                                <div class="bg-secondary rounded-xl p-6 text-center">
                                    <div class="font-display text-4xl font-bold text-purple-400 mb-2">5+</div>
                                    <div class="text-gray-400">Tim Profesional</div>
                                </div>
                                <div class="bg-secondary rounded-xl p-6 text-center">
                                    <div class="font-display text-4xl font-bold text-orange-400 mb-2">5+</div>
                                    <div class="text-gray-400">Tahun Pengalaman</div>
                                </div>
                            </div>
                        </div>
                        <div
                            class="absolute -top-4 -right-4 w-full h-full bg-gradient-to-br from-accent/20 to-accentBlue/20 rounded-2xl">
                        </div>
                    </div>
                </div>

                <div class="order-1 lg:order-2">
                    <span
                        class="reveal inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                        <Icon name="info" class="w-4 h-4" />
                        Tentang Kami
                    </span>
                    <h2 class="reveal reveal-delay-1 font-display text-3xl sm:text-4xl lg:text-5xl font-bold mb-6">
                        Partner <span class="text-accent">Terpercaya</span> untuk Transformasi Digital
                    </h2>
                    <div class="reveal reveal-delay-2 space-y-4 text-gray-400">
                        <p>
                            <strong class="text-white">TD Digital</strong> adalah startup teknologi yang berfokus pada
                            pengembangan solusi digital untuk institusi pendidikan, pemerintahan, dan bisnis di
                            Indonesia.
                        </p>
                        <p>
                            Didirikan pada tahun 2019, kami telah membantu lebih dari 150 klien dalam melakukan
                            transformasi digital dengan menghadirkan aplikasi yang inovatif, aman, dan mudah digunakan.
                        </p>
                    </div>

                    <div class="reveal reveal-delay-3 mt-8 space-y-4">
                        <div class="flex items-start gap-4">
                            <div
                                class="w-10 h-10 rounded-lg bg-accent/10 flex items-center justify-center flex-shrink-0 mt-1">
                                <Icon name="target" class="w-5 h-5 text-accent" />
                            </div>
                            <div>
                                <h4 class="font-semibold text-white mb-1">Visi Kami</h4>
                                <p class="text-gray-400 text-sm">Menjadi perusahaan teknologi terdepan dalam memberikan
                                    solusi digital yang berkualitas dan terjangkau.</p>
                            </div>
                        </div>
                        <div class="flex items-start gap-4">
                            <div
                                class="w-10 h-10 rounded-lg bg-accentBlue/10 flex items-center justify-center flex-shrink-0 mt-1">
                                <Icon name="compass" class="w-5 h-5 text-accentBlue" />
                            </div>
                            <div>
                                <h4 class="font-semibold text-white mb-1">Misi Kami</h4>
                                <p class="text-gray-400 text-sm">Menyediakan layanan pengembangan aplikasi dengan
                                    standar kualitas tinggi, harga kompetitif, dan dukungan teknis yang responsif.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="kontak" class="py-24 relative bg-secondary/50">
        <div class="gradient-orb w-72 h-72 bg-accent/30 bottom-0 left-0"></div>

        <div class="max-w-7xl mx-auto px-6">
            <div class="text-center mb-16">
                <span
                    class="reveal inline-flex items-center gap-2 px-4 py-2 rounded-full bg-card border border-border text-accent text-sm font-medium mb-6">
                    <Icon name="mail" class="w-4 h-4" />
                    Hubungi Kami
                </span>
                <h2 class="reveal reveal-delay-1 font-display text-3xl sm:text-4xl lg:text-5xl font-bold mb-6">
                    Siap Memulai <span class="text-accent">Proyek</span> Anda?
                </h2>
                <p class="reveal reveal-delay-2 text-gray-400 max-w-2xl mx-auto">
                    Konsultasikan kebutuhan digital Anda dengan tim kami secara gratis
                </p>
            </div>

            <div class="grid lg:grid-cols-2 gap-12">
                <div class="reveal">
                    <form id="contactForm" @submit.prevent="submitContactForm" class="bg-card rounded-2xl border border-border p-8 space-y-6">
                        <div>
                            <label for="name" class="block text-sm font-medium mb-2">Nama Lengkap</label>
                            <input type="text" id="name" name="name" v-model="contactForm.name" required
                                class="w-full bg-secondary border border-border rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:border-accent focus:outline-none transition-colors"
                                placeholder="Masukkan nama Anda">
                        </div>
                        <div>
                            <label for="email" class="block text-sm font-medium mb-2">Email</label>
                            <input type="email" id="email" name="email" v-model="contactForm.email" required
                                class="w-full bg-secondary border border-border rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:border-accent focus:outline-none transition-colors"
                                placeholder="email@example.com">
                        </div>
                        <div>
                            <label for="subject" class="block text-sm font-medium mb-2">Subjek</label>
                            <select id="subject" name="subject" v-model="contactForm.subject"
                                class="w-full bg-secondary border border-border rounded-xl px-4 py-3 text-white focus:border-accent focus:outline-none transition-colors">
                                <option value="">Pilih layanan</option>
                                <option value="absensi">Aplikasi Absensi</option>
                                <option value="evoting">Sistem E-Voting</option>
                                <option value="sischool">Sistem Informasi Sekolah</option>
                                <option value="website">Website Company Profile</option>
                                <option value="custom">Aplikasi Custom</option>
                            </select>
                        </div>
                        <div>
                            <label for="message" class="block text-sm font-medium mb-2">Pesan</label>
                            <textarea id="message" name="message" v-model="contactForm.message" rows="4" required
                                class="w-full bg-secondary border border-border rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:border-accent focus:outline-none transition-colors resize-none"
                                placeholder="Ceritakan kebutuhan proyek Anda..."></textarea>
                        </div>
                        <button type="submit" :disabled="isSubmitting"
                            :class="{ 'bg-green-500 text-white': formStatus === 'sent', 'btn-primary': formStatus !== 'sent' }"
                            class="w-full py-4 rounded-xl font-semibold text-primary flex items-center justify-center gap-2">
                            <Icon v-if="isSubmitting" name="loader-2" class="w-5 h-5 animate-spin" />
                            <Icon v-else-if="formStatus === 'sent'" name="check" class="w-5 h-5" />
                            <Icon v-else name="send" class="w-5 h-5" />
                            {{ isSubmitting ? 'Mengirim...' : formStatus === 'sent' ? 'Terkirim!' : 'Kirim Pesan' }}
                        </button>
                    </form>
                </div>

                <div class="reveal reveal-delay-1 space-y-8">
                    <div class="bg-card rounded-2xl border border-border p-6">
                        <h3 class="font-display text-xl font-semibold mb-6">Informasi Kontak</h3>
                        <div class="space-y-4">
                            <div class="flex items-center gap-4">
                                <div class="w-12 h-12 rounded-xl bg-accent/10 flex items-center justify-center">
                                    <Icon name="mail" class="w-5 h-5 text-accent" />
                                </div>
                                <div>
                                    <div class="text-gray-500 text-sm">Email</div>
                                    <a href="mailto:hello@diginusa.id"
                                        class="text-white hover:text-accent transition-colors">tekomdevdigital@gmail.comd</a>
                                </div>
                            </div>
                            <div class="flex items-center gap-4">
                                <div class="w-12 h-12 rounded-xl bg-green-500/10 flex items-center justify-center">
                                    <Icon name="message-circle" class="w-5 h-5 text-green-500" />
                                </div>
                                <div>
                                    <div class="text-gray-500 text-sm">WhatsApp</div>
                                    <a href="https://wa.me/62859106513667" target="_blank" rel="noopener"
                                        class="text-white hover:text-green-500 transition-colors">+62 8591-0651-3667</a>
                                </div>
                            </div>
                            <div class="flex items-center gap-4">
                                <div class="w-12 h-12 rounded-xl bg-accentBlue/10 flex items-center justify-center">
                                    <Icon name="map-pin" class="w-5 h-5 text-accentBlue" />
                                </div>
                                <div>
                                    <div class="text-gray-500 text-sm">Lokasi</div>
                                    <span class="text-white">Jl. Andi Bintang, Kota Palopo</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-card rounded-2xl border border-border p-6">
                        <h3 class="font-display text-xl font-semibold mb-4">Jam Operasional</h3>
                        <div class="space-y-2 text-gray-400">
                            <div class="flex justify-between">
                                <span>Senin - Jumat</span>
                                <span class="text-white">08:00 - 17:00</span>
                            </div>
                            <div class="flex justify-between">
                                <span>Sabtu</span>
                                <span class="text-white">09:00 - 14:00</span>
                            </div>
                            <div class="flex justify-between">
                                <span>Minggu</span>
                                <span class="text-gray-500">Tutup</span>
                            </div>
                        </div>
                    </div>

                    <div
                        class="bg-gradient-to-r from-accent/10 to-accentBlue/10 rounded-2xl border border-accent/20 p-6">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-full bg-accent flex items-center justify-center">
                                <Icon name="headphones" class="w-6 h-6 text-primary" />
                            </div>
                            <div>
                                <div class="font-semibold mb-1">Butuh Bantuan Cepat?</div>
                                <p class="text-gray-400 text-sm">Tim support kami siap membantu 24/7</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-16 bg-secondary border-t border-border">
        <div class="max-w-7xl mx-auto px-6">
            <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-12 mb-12">
                <div>
                    <a @click="handleAnchorClick" href="#" class="flex items-center gap-2 mb-6">
                        <div class="w-10 h-10 from-accent to-accentBlue flex items-center justify-center">
                            <img src="../asset/img/logo3.png" alt="Logo TD Digital" class="">
                        </div>
                        <span class="font-display font-bold text-xl text-white">TD Digital</span>
                    </a>
                    <p class="text-gray-400 mb-6">
                        Startup teknologi yang berfokus pada pengembangan solusi digital untuk institusi pendidikan,
                        pemerintahan, dan bisnis.
                    </p>
                    <div class="flex gap-3">
                        <a href="https://www.youtube.com/@tddigitalofficial"
                            class="w-10 h-10 rounded-full bg-card border border-border flex items-center justify-center text-gray-400 hover:text-accent hover:border-accent transition-colors"
                            aria-label="YouTube DigiNusa">
                            <Icon name="youtube" class="w-5 h-5" />
                        </a>
                        <a @click="handleAnchorClick" href="#"
                            class="w-10 h-10 rounded-full bg-card border border-border flex items-center justify-center text-gray-400 hover:text-accent hover:border-accent transition-colors"
                            aria-label="Instagram DigiNusa">
                            <Icon name="instagram" class="w-5 h-5" />
                        </a>
                        <a @click="handleAnchorClick" href="#"
                            class="w-10 h-10 rounded-full bg-card border border-border flex items-center justify-center text-gray-400 hover:text-accent hover:border-accent transition-colors"
                            aria-label="Facebook DigiNusa">
                            <Icon name="facebook" class="w-5 h-5" />
                        </a>

                    </div>
                </div>

                <div>
                    <h4 class="font-display font-semibold mb-6">Layanan</h4>
                    <ul class="space-y-3">
                        <li><a href="https://oam.tddig.my.id/"
                                class="text-gray-400 hover:text-accent transition-colors">Aplikasi Absensi</a>
                        </li>
                        <li><a href="https://evoting.tddig.my.id/"
                                class="text-gray-400 hover:text-accent transition-colors">Sistem E-Voting</a>
                        </li>
                        <li><a @click="handleAnchorClick" href="#" class="text-gray-400 hover:text-accent transition-colors">Sistem Informasi
                                Sekolah</a></li>
                        <li><a @click="handleAnchorClick" href="#" class="text-gray-400 hover:text-accent transition-colors">Website Company
                                Profile</a></li>
                        <li><a @click="handleAnchorClick" href="#" class="text-gray-400 hover:text-accent transition-colors">Aplikasi Custom</a>
                        </li>
                    </ul>
                </div>

                <div>
                    <h4 class="font-display font-semibold mb-6">Perusahaan</h4>
                    <ul class="space-y-3">
                        <li><a @click="handleAnchorClick" href="#tentang" class="text-gray-400 hover:text-accent transition-colors">Tentang
                                Kami</a></li>
                        <li><a @click="handleAnchorClick" href="#tim" class="text-gray-400 hover:text-accent transition-colors">Tim Kami</a></li>
                        <li><a @click="handleAnchorClick" href="#produk" class="text-gray-400 hover:text-accent transition-colors">Produk</a></li>
                        <li><a @click="handleAnchorClick" href="#portfolio" class="text-gray-400 hover:text-accent transition-colors">Portfolio</a>
                        </li>
                        <li><a @click="handleAnchorClick" href="#" class="text-gray-400 hover:text-accent transition-colors">Karir</a></li>
                        <li><a @click="handleAnchorClick" href="#kontak" class="text-gray-400 hover:text-accent transition-colors">Kontak</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="font-display font-semibold mb-6">Newsletter</h4>
                    <p class="text-gray-400 mb-4">Dapatkan update terbaru tentang produk dan layanan kami.</p>
                    <form class="flex gap-2" @submit.prevent>
                        <input type="email" placeholder="Email Anda"
                            class="flex-1 bg-card border border-border rounded-lg px-4 py-2 text-white placeholder-gray-500 focus:border-accent focus:outline-none transition-colors">
                        <button type="submit" class="btn-primary px-4 py-2 rounded-lg text-primary"
                            aria-label="Subscribe newsletter">
                            <Icon name="arrow-right" class="w-5 h-5" />
                        </button>
                    </form>
                </div>
            </div>

            <div class="border-t border-border pt-8 flex flex-col sm:flex-row justify-between items-center gap-4">
                <p class="text-gray-500 text-sm text-center sm:text-left">
                    &copy; 2026 TD Digital. Seluruh hak cipta dilindungi.
                </p>
                <div class="flex gap-6 text-sm">
                    <a @click="handleAnchorClick" href="#" class="text-gray-500 hover:text-accent transition-colors">Kebijakan Privasi</a>
                    <a @click="handleAnchorClick" href="#" class="text-gray-500 hover:text-accent transition-colors">Syarat & Ketentuan</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- WhatsApp Floating Button -->
    <a href="https://wa.me/62859106513667" target="_blank" rel="noopener"
        class="fixed bottom-6 right-6 w-14 h-14 bg-green-500 rounded-full flex items-center justify-center shadow-lg hover:bg-green-600 hover:scale-110 transition-all z-40 pulse-glow"
        aria-label="Chat via WhatsApp">
        <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="white">
            <path
                d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z" />
        </svg>
    </a>

    <!-- Video Modal -->
    <div id="videoModal" @click.self="closeVideo" :class="{ active: videoFrameSrc }" :style="{ opacity: videoFrameSrc ? 1 : 0, visibility: videoFrameSrc ? 'visible' : 'hidden' }" class="video-modal fixed inset-0 bg-black/90 z-50 flex items-center justify-center p-6">
        <div class="relative w-full max-w-4xl">
            <button id="closeVideoModal" @click="closeVideo"
                class="absolute -top-12 right-0 w-10 h-10 rounded-full bg-white/10 flex items-center justify-center text-white hover:bg-white/20 transition-colors"
                aria-label="Close video">
                <Icon name="x" class="w-6 h-6" />
            </button>
            <div class="aspect-video bg-card rounded-2xl overflow-hidden">
                <iframe id="videoFrame" class="w-full h-full" :src="videoFrameSrc" title="DigiNusa Video Demo" frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen></iframe>
            </div>
        </div>
    </div>
</template>

<script setup>
import { computed, onBeforeUnmount, onMounted, ref } from 'vue'
import Icon from './components/Icon.vue'

const mobileMenuOpen = ref(false)
const isScrolled = ref(false)
const particles = ref([])
const currentSlide = ref(0)
const slidesPerView = ref(1)
const totalSlides = 5
const maxSlide = computed(() => Math.max(0, totalSlides - slidesPerView.value))
const dotCount = computed(() => maxSlide.value + 1)
const videoFrameSrc = ref('')
const contactForm = ref({ name: '', email: '', subject: '', message: '' })
const formStatus = ref('idle')
const isSubmitting = computed(() => formStatus.value === 'sending' || formStatus.value === 'sent')

let autoplayInterval
let revealObserver
let submitTimer
let resetFormTimer

function openMobileMenu() {
  mobileMenuOpen.value = true
  document.body.style.overflow = 'hidden'
}

function closeMobileMenu() {
  mobileMenuOpen.value = false
  if (!videoFrameSrc.value) document.body.style.overflow = ''
}

function handleScroll() {
  isScrolled.value = window.scrollY > 50
}

function handleAnchorClick(event) {
  const href = event.currentTarget.getAttribute('href')
  closeMobileMenu()
  if (!href || !href.startsWith('#')) return

  event.preventDefault()
  if (href === '#') return
  const target = document.querySelector(href)
  if (!target) return
  const headerOffset = 80
  const offsetPosition = target.getBoundingClientRect().top + window.scrollY - headerOffset
  window.scrollTo({ top: offsetPosition, behavior: 'smooth' })
}

function updateSlidesPerView() {
  if (window.innerWidth >= 1024 && mobileMenuOpen.value) closeMobileMenu()
  if (window.innerWidth >= 1024) slidesPerView.value = 3
  else if (window.innerWidth >= 768) slidesPerView.value = 2
  else slidesPerView.value = 1
  currentSlide.value = Math.min(currentSlide.value, maxSlide.value)
}

function goToSlide(index) {
  currentSlide.value = Math.max(0, Math.min(index, maxSlide.value))
}

function previousSlide() {
  goToSlide(currentSlide.value - 1)
}

function nextSlide() {
  goToSlide(currentSlide.value + 1)
}

function advanceSlide() {
  currentSlide.value = currentSlide.value >= maxSlide.value ? 0 : currentSlide.value + 1
}

function startAutoplay() {
  clearInterval(autoplayInterval)
  autoplayInterval = window.setInterval(advanceSlide, 5000)
}

function pauseAutoplay() {
  clearInterval(autoplayInterval)
}

function resumeAutoplay() {
  startAutoplay()
}

function openVideoModal() {
  videoFrameSrc.value = 'https://www.youtube.com/embed/K16R3t1njgQ?autoplay=1'
  document.body.style.overflow = 'hidden'
}

function closeVideo() {
  videoFrameSrc.value = ''
  document.body.style.overflow = ''
}

function handleKeydown(event) {
  if (event.key === 'Escape' && videoFrameSrc.value) closeVideo()
  if (event.key === 'Escape' && mobileMenuOpen.value) closeMobileMenu()
}

function submitContactForm() {
  if (formStatus.value !== 'idle') return
  formStatus.value = 'sending'
  submitTimer = window.setTimeout(() => {
    formStatus.value = 'sent'
    resetFormTimer = window.setTimeout(() => {
      contactForm.value = { name: '', email: '', subject: '', message: '' }
      formStatus.value = 'idle'
    }, 2000)
  }, 1500)
}

onMounted(() => {
  particles.value = Array.from({ length: 20 }, (_, id) => ({
    id,
    style: {
      left: Math.random() * 100 + '%',
      animationDelay: Math.random() * 20 + 's',
      animationDuration: 15 + Math.random() * 10 + 's',
    },
  }))

  handleScroll()
  window.addEventListener('scroll', handleScroll, { passive: true })
  window.addEventListener('resize', updateSlidesPerView)
  document.addEventListener('keydown', handleKeydown)
  updateSlidesPerView()
  startAutoplay()

  revealObserver = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('active')
        revealObserver.unobserve(entry.target)
      }
    })
  }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' })
  document.querySelectorAll('.reveal').forEach((element) => revealObserver.observe(element))
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
  window.removeEventListener('resize', updateSlidesPerView)
  document.removeEventListener('keydown', handleKeydown)
  clearInterval(autoplayInterval)
  clearTimeout(submitTimer)
  clearTimeout(resetFormTimer)
  revealObserver?.disconnect()
  document.body.style.overflow = ''
})
</script>
<style>
/* Component-specific styles remain in src/style.css to preserve the original template. */
</style>
