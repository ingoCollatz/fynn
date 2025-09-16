<script lang="ts">
  export let title: string;
  export let subtitle: string;
  export let phoneNumber: string = "+49123456789";
  export let onContactClick: () => void = () => {};
</script>

<section class="relative py-20 bg-gradient-to-br from-white via-gray-50 to-green-50 overflow-hidden">
  <!-- Decorative Elements -->
  <div class="absolute inset-0">
    <div class="absolute top-10 left-10 w-64 h-64 bg-green-100 rounded-full filter blur-3xl opacity-20"></div>
    <div class="absolute bottom-10 right-10 w-64 h-64 bg-blue-100 rounded-full filter blur-3xl opacity-20"></div>
  </div>
  
  <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
    <h2 class="text-3xl md:text-4xl font-bold mb-6 text-gray-800">
      {title}
    </h2>
    <p class="text-xl mb-8 text-gray-600 max-w-2xl mx-auto">
      {subtitle}
    </p>
    <div class="flex flex-col sm:flex-row gap-4 justify-center">
      <a 
        href="tel:{phoneNumber}"
        class="bg-white text-green-600 px-8 py-4 rounded-xl font-semibold hover:bg-green-50 transition-all duration-200 inline-flex items-center justify-center space-x-2 shadow-lg hover:shadow-xl border border-green-100"
      >
        <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
          <path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74a1 1 0 01.836.986V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z"/>
        </svg>
        <span>Jetzt anrufen</span>
      </a>
      <button 
        on:click={onContactClick}
        class="bg-green-600 hover:bg-green-700 text-white px-8 py-4 rounded-xl font-semibold transition-all duration-200 shadow-lg hover:shadow-xl"
      >
        Kostenloses Angebot anfordern
      </button>
    </div>
  </div>
</section>