<script lang="ts">
  function scrollToContact() {
    const contactElement = document.getElementById('contact');
    if (contactElement) {
      contactElement.scrollIntoView({ behavior: 'smooth' });
    }
  }
</script>

<section id="home" class="relative min-h-screen bg-gradient-to-br from-slate-50 to-blue-50 flex items-center">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
    <div class="grid lg:grid-cols-2 gap-12 items-center">
      
      <!-- Left Content -->
      <div class="space-y-8">
        <!-- Badge -->
        <div class="inline-flex items-center px-4 py-2 rounded-full bg-blue-100 text-blue-800 text-sm font-medium">
          <span class="w-2 h-2 bg-blue-500 rounded-full mr-2"></span>
          Professioneller Service seit Jahren
        </div>

        <!-- Main Heading -->
        <div class="space-y-4">
          <h1 class="text-5xl lg:text-6xl font-bold text-gray-900 leading-tight">
            Fynn Schomann
          </h1>
          <h2 class="text-2xl lg:text-3xl font-semibold text-blue-600">
            Hausmeisterservice & Gartenpflege
          </h2>
        </div>

        <!-- Description -->
        <p class="text-xl text-gray-600 leading-relaxed">
          Ihr zuverlässiger Partner für professionelle Hausmeisterservices und Gartenpflege. 
          Qualität, Pünktlichkeit und faire Preise – darauf können Sie sich verlassen.
        </p>

        <!-- Key Points -->
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
        </div>

        <!-- CTA Buttons -->
        <div class="flex flex-col sm:flex-row gap-4">
          <button 
            class="bg-blue-600 text-white px-8 py-4 rounded-lg font-semibold hover:bg-blue-700 transition-colors shadow-lg hover:shadow-xl transform hover:-translate-y-0.5 duration-200"
            on:click={scrollToContact}
          >
            Kostenlose Beratung anfragen
          </button>
          
          <a 
            href="tel:+49123456789" 
            class="bg-white border-2 border-gray-200 text-gray-900 px-8 py-4 rounded-lg font-semibold hover:border-blue-300 hover:bg-blue-50 transition-all duration-200 text-center"
          >
            📞 +49 123 456 789
          </a>
        </div>
      </div>

      <!-- Right Visual -->
      <div class="relative">
        <div class="bg-gradient-to-br from-blue-500 to-purple-600 rounded-3xl p-8 shadow-2xl">
          <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-6 space-y-4">
            <div class="flex items-center justify-between text-white">
              <span class="text-lg font-semibold">Unsere Services</span>
              <span class="text-2xl">🏠</span>
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
</section>
