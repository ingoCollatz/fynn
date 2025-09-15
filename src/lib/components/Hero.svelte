<script lang="ts">
  import Logo from '$lib/assets/Logo.svelte';
  import SimpleIcon from './SimpleIcon.svelte';
  import { onMount } from 'svelte';
  
  let parallaxElement: HTMLElement;
  let scrollY = 0;
  
  onMount(() => {
    const handleScroll = () => {
      scrollY = window.scrollY;
      if (parallaxElement) {
        const speed = 0.5; // Adjust this value to control parallax speed
        parallaxElement.style.transform = `translateY(${scrollY * speed}px)`;
      }
    };
    
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
  
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

<section id="home" class="relative min-h-screen flex items-center overflow-hidden scroll-mt-20">
  <!-- Background Image -->
  <div class="absolute inset-0 bg-gradient-to-br from-green-50 via-amber-50 to-orange-50"></div>
    <!-- Background Image with Parallax -->
  <div 
    bind:this={parallaxElement}
    class="absolute inset-0 w-full h-[120%] bg-cover bg-center bg-no-repeat opacity-60 will-change-transform"
    style="background-image: url('https://images.unsplash.com/photo-1570129477492-45c003edd2be?ixlib=rb-4.0.3&auto=format&fit=crop&w=2000&q=80'); top: -10%;"
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
          
          <a 
            href="https://wa.me/49123456789" 
            target="_blank"
            rel="noopener noreferrer"
            class="bg-white border-2 border-gray-200 text-gray-900 px-8 py-4 rounded-lg font-semibold hover:border-green-300 hover:bg-green-50 transition-all duration-200 flex items-center justify-center space-x-2"
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
            <div class="space-y-3">
              <div class="bg-white/20 rounded-lg p-3 flex items-center space-x-3">
                <span class="text-xl">🗑️</span>
                <span class="text-white font-medium">Entrümplung</span>
              </div>
              <div class="bg-white/20 rounded-lg p-3 flex items-center space-x-3">
                <span class="text-xl">✨</span>
                <span class="text-white font-medium">Reinigungsservice</span>
              </div>
              <div class="bg-white/20 rounded-lg p-3 flex items-center space-x-3">
                <span class="text-xl">🔧</span>
                <span class="text-white font-medium">Hausmeisterservice</span>
              </div>
              <div class="bg-white/20 rounded-lg p-3 flex items-center space-x-3">
                <span class="text-xl">❄️</span>
                <span class="text-white font-medium">Winterdienst</span>
              </div>
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
