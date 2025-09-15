<script lang="ts">
  import HeaderLogo from '$lib/assets/HeaderLogo.svelte';
  import SimpleIcon from './SimpleIcon.svelte';
  import { onMount } from 'svelte';
  
  let mobileMenuOpen = false;
  let scrollY = 0;
  let isScrolled = false;
  
  // Calculate logo size based on scroll position
  $: logoSize = isScrolled ? "200" : "280";
  $: headerHeight = isScrolled ? "h-16" : "h-24";
  
  onMount(() => {
    const handleScroll = () => {
      scrollY = window.scrollY;
      isScrolled = scrollY > 50;
    };
    
    window.addEventListener('scroll', handleScroll);
    handleScroll(); // Initial call
    
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });
  
  function toggleMobileMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
  
  function closeMobileMenu() {
    mobileMenuOpen = false;
  }

  function scrollToSection(sectionId: string) {
    // Special case for home - scroll to absolute top
    if (sectionId === 'home') {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
      closeMobileMenu();
      return;
    }
    
    const element = document.getElementById(sectionId);
    if (element) {
      const headerHeight = 80; // Account for fixed header height
      const elementPosition = element.offsetTop - headerHeight;
      window.scrollTo({
        top: elementPosition,
        behavior: 'smooth'
      });
    }
    closeMobileMenu();
  }
</script>

<header class="bg-white/95 backdrop-blur-md shadow-sm sticky top-0 z-50 border-b border-gray-100 transition-all duration-300">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center {headerHeight} transition-all duration-300">
      
      <!-- Logo/Brand -->
      <div class="flex items-center">
        <HeaderLogo 
          size={logoSize} 
          className="hover:scale-105 transition-all duration-300 cursor-pointer" 
        />
      </div>
      
      <!-- Desktop Navigation -->
      <nav class="hidden lg:flex items-center space-x-8">
        <button 
          on:click={() => scrollToSection('home')}
          class="text-gray-700 hover:text-blue-600 font-medium transition-colors relative group"
        >
          Start
          <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-600 transition-all duration-300 group-hover:w-full"></span>
        </button>
        <button 
          on:click={() => scrollToSection('about')}
          class="text-gray-700 hover:text-blue-600 font-medium transition-colors relative group"
        >
          Über mich
          <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-600 transition-all duration-300 group-hover:w-full"></span>
        </button>
        <button 
          on:click={() => scrollToSection('services')}
          class="text-gray-700 hover:text-blue-600 font-medium transition-colors relative group"
        >
          Leistungen
          <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-600 transition-all duration-300 group-hover:w-full"></span>
        </button>
        <button 
          on:click={() => scrollToSection('contact')}
          class="text-gray-700 hover:text-blue-600 font-medium transition-colors relative group"
        >
          Kontakt
          <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-600 transition-all duration-300 group-hover:w-full"></span>
        </button>
      </nav>
      
      <!-- CTA Buttons -->
      <div class="hidden md:flex items-center space-x-4">
        <div class="text-blue-600 font-medium flex items-center space-x-2">
          <svg class="w-4 h-4 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
          </svg>
          <span class="hidden xl:inline">+49 123 456 789</span>
        </div>
        <button 
          class="bg-blue-600 text-white px-6 py-2.5 rounded-lg font-medium hover:bg-blue-700 transition-all duration-200 transform hover:-translate-y-0.5 shadow-lg hover:shadow-xl"
          on:click={() => scrollToSection('contact')}
        >
          Beratung anfragen
        </button>
      </div>
      
      <!-- Mobile Menu Button -->
      <button 
        class="lg:hidden p-2 text-gray-700 hover:text-blue-600 transition-colors"
        on:click={toggleMobileMenu}
        aria-label="Menü öffnen oder schließen"
      >
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          {#if mobileMenuOpen}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          {:else}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          {/if}
        </svg>
      </button>
    </div>
    
    <!-- Mobile Navigation -->
    {#if mobileMenuOpen}
      <div class="lg:hidden border-t border-gray-100 py-4">
        <nav class="flex flex-col space-y-4">
          <button 
            class="text-left text-gray-700 hover:text-blue-600 font-medium transition-colors py-2"
            on:click={() => scrollToSection('home')}
          >
            Start
          </button>
          <button 
            class="text-left text-gray-700 hover:text-blue-600 font-medium transition-colors py-2"
            on:click={() => scrollToSection('about')}
          >
            Über mich
          </button>
          <button 
            class="text-left text-gray-700 hover:text-blue-600 font-medium transition-colors py-2"
            on:click={() => scrollToSection('services')}
          >
            Leistungen
          </button>
          <button 
            class="text-left text-gray-700 hover:text-blue-600 font-medium transition-colors py-2"
            on:click={() => scrollToSection('contact')}
          >
            Kontakt
          </button>
          <div class="pt-4 border-t border-gray-100 space-y-3">
            <a 
              href="tel:+49123456789" 
              class="flex items-center space-x-2 text-blue-600 font-medium"
            >
              <svg class="w-4 h-4 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
              </svg>
              <span>+49 123 456 789</span>
            </a>
            <a 
              href="https://wa.me/49123456789" 
              target="_blank"
              rel="noopener noreferrer"
              class="flex items-center space-x-2 text-green-600 font-medium"
            >
              <SimpleIcon name="whatsapp" size="16" className="text-green-600" />
              <span>WhatsApp Chat</span>
            </a>
            <button 
              class="w-full bg-blue-600 text-white px-6 py-3 rounded-lg font-medium hover:bg-blue-700 transition-colors"
              on:click={() => scrollToSection('contact')}
            >
              Beratung anfragen
            </button>
          </div>
        </nav>
      </div>
    {/if}
  </div>
</header>
