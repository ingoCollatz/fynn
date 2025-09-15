<script lang="ts">
  import SimpleIcon from './SimpleIcon.svelte';
</script>

<footer class="bg-gradient-to-br from-gray-900 via-gray-800 to-green-900 text-gray-300 py-16 px-6 relative overflow-hidden">
  <!-- Background Elements -->
  <div class="absolute top-0 left-0 w-72 h-72 bg-green-500/10 rounded-full -translate-x-36 -translate-y-36 blur-3xl"></div>
  <div class="absolute bottom-0 right-0 w-96 h-96 bg-blue-500/10 rounded-full translate-x-48 translate-y-48 blur-3xl"></div>
  <div class="absolute top-1/2 left-1/2 w-64 h-64 bg-purple-500/10 rounded-full -translate-x-32 -translate-y-32 blur-3xl"></div>
  
  <div class="max-w-7xl mx-auto relative z-10">
    <div class="text-center space-y-8">
      <!-- Logo/Brand Section -->
      <div class="space-y-4">
        <h3 class="text-2xl font-bold text-white">Fynn Schomann</h3>
        <p class="text-gray-400 max-w-2xl mx-auto">
          Hausmeisterservice & Gartenpflege - Ihr zuverlässiger Partner für professionelle Dienstleistungen rund um Haus und Garten.
        </p>
      </div>
      
      <!-- Contact Info -->
      <div class="flex flex-col sm:flex-row justify-center items-center gap-8 py-8">
        <div class="flex items-center space-x-3">
          <div class="w-10 h-10 bg-green-500/20 rounded-full flex items-center justify-center">
            <svg class="w-5 h-5 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
            </svg>
          </div>
          <span class="text-gray-300">+49 123 456 789</span>
        </div>
        <div class="flex items-center space-x-3">
          <div class="w-10 h-10 bg-green-500/20 rounded-full flex items-center justify-center">
            <SimpleIcon name="whatsapp" size="20" className="text-green-400" />
          </div>
          <span class="text-gray-300">WhatsApp verfügbar</span>
        </div>
      </div>
      
      <!-- Divider -->
      <div class="border-t border-gray-700 pt-8">
        <div class="flex flex-col sm:flex-row justify-between items-center gap-4">
          <p class="text-gray-400">© {new Date().getFullYear()} Fynn Schomann Hausmeisterservice & Gartenpflege</p>
          <div class="flex space-x-6">
            <a href="/impressum" class="text-gray-400 hover:text-white transition-colors duration-300">Impressum</a>
            <a href="/datenschutz" class="text-gray-400 hover:text-white transition-colors duration-300">Datenschutz</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</footer>
