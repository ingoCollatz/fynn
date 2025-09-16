<script lang="ts">
  import { onMount } from 'svelte';
  
  let scrollY = 0;
  let isMobile = false;
  
  onMount(() => {
    // Detect mobile devices
    isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent) || window.innerWidth < 768;
  });
  
  // Parallax transform calculation - disable on mobile to prevent stuttering
  $: parallaxTransform = isMobile ? 'translateY(0px)' : `translateY(${scrollY * 0.3}px)`;

  const services = [
    { 
      icon: "�️", 
      title: "Entrümplung", 
      desc: "Professionelle Entrümpelung von Häusern, Wohnungen, Kellern und Dachböden. Fachgerechte Entsorgung inklusive.",
      features: ["Haushaltsauflösungen", "Kellerentrümplung", "Entsorgung inklusive"]
    },
    { 
      icon: "✨", 
      title: "Außen- & Innenreinigung", 
      desc: "Gründliche Reinigung von Gebäuden innen und außen. Von der Glasreinigung bis zur Tiefenreinigung.",
      features: ["Fassadenreinigung", "Fensterreinigung", "Grundreinigung"]
    },
    { 
      icon: "🔧", 
      title: "Hausmeisterservice", 
      desc: "Umfassende Betreuung und Wartung Ihrer Immobilie. Regelmäßige Kontrollen und schnelle Reparaturen.",
      features: ["Objektbetreuung", "Wartungsarbeiten", "Kleinreparaturen"]
    },
    { 
      icon: "❄️", 
      title: "Winterdienst", 
      desc: "Zuverlässiger Räum- und Streudienst in der kalten Jahreszeit. Pünktlich und verkehrssicher.",
      features: ["Schneeräumung", "Streudienst", "Eisentfernung"]
    },
    { 
      icon: "🏗️", 
      title: "Einbau von Fertigbauteilen", 
      desc: "Fachgerechte Montage und Installation von Fertigbauteilen. Präzise Arbeit mit professionellem Werkzeug.",
      features: ["Montagearbeiten", "Installationen", "Anschlussarbeiten"]
    }
  ];

  function scrollToContact() {
    const contactElement = document.getElementById('contact');
    if (contactElement) {
      const headerHeight = 80; // Account for fixed header height
      const elementPosition = contactElement.offsetTop - headerHeight;
      window.scrollTo({
        top: elementPosition,
        behavior: 'smooth'
      });
    }
  }
</script>

<svelte:window bind:scrollY={scrollY} />

<section id="services" class="py-20 bg-gradient-to-br from-gray-50 via-green-50 to-blue-50 relative overflow-hidden scroll-mt-20">
  <!-- Background Image with Parallax -->
  <div 
    class="absolute inset-0 w-full h-[150%] -top-[50%] bg-cover bg-center bg-no-repeat opacity-60 will-change-transform
           bg-[url('https://images.unsplash.com/photo-1560518883-ce09059eeffa?ixlib=rb-4.0.3&auto=format&fit=crop&w=2000&q=80')]"
    style:transform={parallaxTransform}
  ></div>
  
  <!-- Decorative Background Elements -->
  <div class="absolute top-0 left-0 w-72 h-72 bg-green-200/30 rounded-full -translate-x-36 -translate-y-36 blur-3xl"></div>
  <div class="absolute bottom-0 right-0 w-96 h-96 bg-blue-200/30 rounded-full translate-x-48 translate-y-48 blur-3xl"></div>
  <div class="absolute top-1/2 left-1/2 w-64 h-64 bg-purple-200/20 rounded-full -translate-x-32 -translate-y-32 blur-3xl"></div>
  
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
    <!-- Main Services Card -->
    <div class="bg-white/20 backdrop-blur-lg rounded-3xl shadow-2xl p-8 lg:p-12 border border-white/20">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
          Meine Leistungen
        </h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Professionelle Dienstleistungen für Ihr Zuhause und Ihre Immobilie. 
          Zuverlässig, sauber und fair – darauf können Sie sich verlassen.
        </p>
      </div>

      <!-- Services Grid - Compact -->
      <div class="grid md:grid-cols-2 gap-8 mb-16">
        {#each services as service}
          <div class="flex items-start gap-4 p-6 rounded-xl bg-gray-50/50 hover:bg-white/70 transition-all duration-300 border border-gray-100/50">

            
            <!-- Content -->
            <div class="flex-1 min-w-0">
              <h3 class="text-xl font-bold text-gray-900 mb-2">{service.title}</h3>
              <p class="text-sm text-gray-600 leading-relaxed">{service.desc}</p>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>
