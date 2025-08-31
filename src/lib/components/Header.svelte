<script>
  let mobileMenuOpen = false;
  
  function toggleMobileMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
  
  function closeMobileMenu() {
    mobileMenuOpen = false;
  }
</script>

<header class="bg-white shadow-md sticky top-0 z-50">
  <nav class="max-w-6xl mx-auto px-6 py-4">
    <div class="flex justify-between items-center">
      <!-- Logo/Brand -->
      <div class="text-xl font-bold text-blue-600">
        🔨 Handwerker Frankfurt
      </div>
      
      <!-- Desktop Navigation -->
      <div class="hidden md:flex space-x-8">
        <a href="#home" class="text-gray-700 hover:text-blue-600 transition-colors">Start</a>
        <a href="#about" class="text-gray-700 hover:text-blue-600 transition-colors">Über uns</a>
        <a href="#services" class="text-gray-700 hover:text-blue-600 transition-colors">Leistungen</a>
        <a href="#portfolio" class="text-gray-700 hover:text-blue-600 transition-colors">Projekte</a>
        <a href="#testimonials" class="text-gray-700 hover:text-blue-600 transition-colors">Bewertungen</a>
        <a href="#contact" class="text-gray-700 hover:text-blue-600 transition-colors">Kontakt</a>
      </div>
      
      <!-- CTA Button -->
      <div class="hidden md:block">
        <a href="#contact" class="bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors">
          Angebot anfordern
        </a>
      </div>
      
      <!-- Mobile Menu Button -->
      <button 
        class="md:hidden text-gray-700"
        on:click={toggleMobileMenu}
        aria-label="Menü öffnen oder schließen"
      >
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
        </svg>
      </button>
    </div>
    
    <!-- Mobile Navigation -->
    {#if mobileMenuOpen}
      <div class="md:hidden mt-4 pb-4 border-t">
        <div class="flex flex-col space-y-2 mt-4">
          <a href="#home" class="text-gray-700 hover:text-blue-600 py-2" on:click={closeMobileMenu}>Start</a>
          <a href="#about" class="text-gray-700 hover:text-blue-600 py-2" on:click={closeMobileMenu}>Über uns</a>
          <a href="#services" class="text-gray-700 hover:text-blue-600 py-2" on:click={closeMobileMenu}>Leistungen</a>
          <a href="#portfolio" class="text-gray-700 hover:text-blue-600 py-2" on:click={closeMobileMenu}>Projekte</a>
          <a href="#testimonials" class="text-gray-700 hover:text-blue-600 py-2" on:click={closeMobileMenu}>Bewertungen</a>
          <a href="#contact" class="text-gray-700 hover:text-blue-600 py-2" on:click={closeMobileMenu}>Kontakt</a>
          <a href="#contact" class="bg-blue-600 text-white px-4 py-2 rounded-lg text-center mt-2" on:click={closeMobileMenu}>
            Angebot anfordern
          </a>
        </div>
      </div>
    {/if}
  </nav>
</header>
