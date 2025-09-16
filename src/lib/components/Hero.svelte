<script lang="ts">
  import Logo from '$lib/assets/Logo.svelte';
  import SimpleIcon from './SimpleIcon.svelte';
  import { onMount } from 'svelte';
  
  let scrollY = 0;
  let isMobile = false;
  let currentSlide = 0;
  let slideInterval: number;
  
  // Services data for slideshow
  const services = [
    {
      name: 'Entrümplung',
      image: 'https://images.unsplash.com/photo-1610459716431-e07abcf74230?w=400&h=300&&fitq=crop&auto=format',
      description: 'Professionelle Entrümpelung von Wohnungen, Häusern und Gewerberäumen'
    },
    {
      name: 'Reinigungsservice',
      image: 'https://images.unsplash.com/photo-1581578731548-c64695cc6952?w=400&h=300&fit=crop&auto=format',
      description: 'Gründliche Reinigung für Privat- und Geschäftskunden'
    },
    {
      name: 'Hausmeisterservice',
      image: 'https://images.unsplash.com/photo-1540103711724-ebf833bde8d1?&w=400&h=300&fit=crop&auto=format',
      description: 'Zuverlässige Hausmeistertätigkeiten und Instandhaltung'
    },
    {
      name: 'Winterdienst',
      image: 'https://images.unsplash.com/photo-1611589053483-9976cc7e5e76?q=80&w=400&h=300&auto=format&fit=crop',
      description: 'Schneeräumung und Streudienst für sichere Wege'
    },
    {
      name: 'Einbau von Fertigbauteilen',
      image: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=400&h=300&fit=crop&auto=format',
      description: 'Fachgerechte Montage von Fertigbauteilen und Konstruktionen'
    },
    {
      name: 'Gartenpflege',
      image: 'https://images.unsplash.com/photo-1416879595882-3373a0480b5b?w=400&h=300&fit=crop&auto=format',
      description: 'Professionelle Gartenpflege und Landschaftsgestaltung'
    }
  ];

  onMount(() => {
    // Detect mobile devices
    isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent) || window.innerWidth < 768;
    
    // Start slideshow
    startSlideshow();
    
    return () => {
      if (slideInterval) {
        clearInterval(slideInterval);
      }
    };
  });

  function startSlideshow() {
    slideInterval = setInterval(() => {
      currentSlide = (currentSlide + 1) % services.length;
    }, 3000); // Change slide every 3 seconds
  }

  function goToSlide(index: number) {
    currentSlide = index;
    // Restart the interval
    if (slideInterval) {
      clearInterval(slideInterval);
    }
    startSlideshow();
  }
  
  // Parallax transform calculation - disable on mobile to prevent stuttering
  $: parallaxTransform = isMobile ? 'translateY(0px)' : `translateY(${scrollY * 0.5}px)`;
  
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
  
  function scrollToServices() {
    const servicesElement = document.getElementById('services');
    if (servicesElement) {
      const headerHeight = 80; // Account for fixed header height
      const elementPosition = servicesElement.offsetTop - headerHeight;
      window.scrollTo({
        top: elementPosition,
        behavior: 'smooth'
      });
    }
  }
</script>

<svelte:window bind:scrollY={scrollY} />

<section id="home" class="relative min-h-screen flex items-center overflow-hidden scroll-mt-20">
  <!-- Background Image -->
  <div class="absolute inset-0 bg-gradient-to-br from-green-50 via-amber-50 to-orange-50"></div>
    <!-- Background Image with Parallax -->
  <div 
    class="absolute inset-0 w-full h-[120%] -top-[10%] bg-cover bg-center bg-no-repeat opacity-60 will-change-transform
           bg-[url('https://images.unsplash.com/photo-1570129477492-45c003edd2be?ixlib=rb-4.0.3&auto=format&fit=crop&w=2000&q=80')]"
    style:transform={parallaxTransform}
  ></div>
  
  <!-- Content Card -->
  <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 w-full">
    <!-- Main Card Container -->
    <div class="bg-white/20 backdrop-blur-lg rounded-3xl shadow-2xl p-8 lg:p-12 border border-white/20">
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        
        <!-- Left Content -->
        <div class="space-y-8">

        <!-- Main Heading -->
        <div class="space-y-4">
          <h1 class="text-4xl lg:text-5xl font-bold text-gray-900 leading-tight">
            Ihr Partner für Haus & Garten
          </h1>
          <h2 class="text-xl lg:text-2xl font-semibold text-green-700">
            Zuverlässig • Professionell • Fair
          </h2>
        </div>

        <!-- Description -->
        <p class="text-xl text-gray-600 leading-relaxed">
          Ihr zuverlässiger Partner für professionelle Hausmeisterservices und Gartenpflege. 
          Qualität, Pünktlichkeit und faire Preise – darauf können Sie sich verlassen.
        </p>

        <!-- Key Points
        <div class="grid sm:grid-cols-3 gap-4">
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-green-500 rounded-full"></div>
            <span class="text-sm font-medium text-gray-700">Zuverlässig</span>
          </div>
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-blue-500 rounded-full"></div>
            <span class="text-sm font-medium text-gray-700">Professionell</span>
          </div>
          <div class="flex items-center space-x-2">
            <div class="w-3 h-3 bg-purple-500 rounded-full"></div>
            <span class="text-sm font-medium text-gray-700">Fair</span>
          </div>
        </div> -->

        <!-- CTA Buttons -->
        <div class="flex flex-col sm:flex-row gap-4">
          <button 
            class="bg-blue-600 text-white px-8 py-4 rounded-lg font-semibold hover:bg-blue-700 transition-colors shadow-lg hover:shadow-xl transform hover:-translate-y-0.5 duration-200"
            on:click={scrollToContact}
          >
            Kostenlose Beratung anfragen
          </button>
          
          <!-- Mobile: Phone Button -->
          <a 
            href="tel:+49123456789"
            class="sm:hidden bg-white border-2 border-gray-200 text-gray-900 px-8 py-4 rounded-lg font-semibold hover:border-blue-300 hover:bg-blue-50 transition-all duration-200 flex items-center justify-center space-x-2"
          >
            <svg class="w-5 h-5 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
            </svg>
            <span>Anrufen</span>
          </a>
          
          <!-- Desktop: WhatsApp Button -->
          <a 
            href="https://wa.me/49123456789" 
            target="_blank"
            rel="noopener noreferrer"
            class="hidden sm:flex bg-white border-2 border-gray-200 text-gray-900 px-8 py-4 rounded-lg font-semibold hover:border-green-300 hover:bg-green-50 transition-all duration-200 items-center justify-center space-x-2"
          >
            <SimpleIcon name="whatsapp" size="20" className="text-green-600" />
            <span>WhatsApp Chat</span>
          </a>
        </div>
      </div>

      <!-- Right Visual -->
      <div class="relative hidden lg:block">
        <div class="bg-gradient-to-br from-blue-500 to-purple-600 rounded-3xl p-8 shadow-2xl">
          <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-6 space-y-4">
            <div class="flex items-center justify-between text-white">
              <span class="text-lg font-semibold">Meine Services</span>
            </div>
            
            <!-- Slideshow Container -->
            <div class="relative overflow-hidden rounded-lg min-h-[280px]">
              <div 
                class="flex transition-transform duration-500 ease-in-out"
                style="transform: translateX(-{currentSlide * 100}%)"
              >
                {#each services as service, index}
                  <div class="w-full flex-shrink-0 px-2">
                    <!-- Current Service Display -->
                    <div class="relative rounded-lg overflow-hidden h-64 group">
                      <!-- Background Image -->
                      <div 
                        class="absolute inset-0 bg-cover bg-center transition-transform duration-300 group-hover:scale-105 opacity-50"
                        style="background-image: url('{service.image}')"
                      ></div>
                      <!-- Overlay -->
                      <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/40 to-transparent"></div>
                      <!-- Content -->
                      <div class="relative h-full flex flex-col justify-end p-6 text-white">
                        <h3 class="text-2xl font-bold mb-2">{service.name}</h3>
                        <p class="text-sm text-white/90 leading-relaxed">{service.description}</p>
                      </div>
                    </div>
                  </div>
                {/each}
              </div>
            </div>
            
            <!-- View All Services Button -->
            <div class="pt-4 border-t border-white/20">
              <button 
                on:click={scrollToServices}
                class="w-full bg-white/20 hover:bg-white/30 backdrop-blur-sm rounded-lg p-3 flex items-center justify-center space-x-2 text-white font-medium transition-all duration-300 hover:scale-105"
              >
                <span>Alle Services ansehen</span>
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
                </svg>
              </button>
            </div>
          </div>
        </div>
        
        <!-- Floating Elements -->
        <div class="absolute -top-4 -right-4 w-24 h-24 bg-yellow-400 rounded-full opacity-20"></div>
        <div class="absolute -bottom-6 -left-6 w-16 h-16 bg-green-400 rounded-full opacity-30"></div>
      </div>

      </div>
    </div>
  </div>
</section>
