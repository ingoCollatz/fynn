<script lang="ts">
  export let title: string;
  export let subtitle: string;
  export let backgroundImage: string;
  export let phoneNumber: string = "+49123456789";
  export let onContactClick: () => void = () => {};
  export let parallaxTransform: string = "translateY(0px)";
</script>

<section class="relative min-h-[60vh] flex items-center overflow-hidden">
  <!-- Background Image -->
  <div class="absolute inset-0">
    <div 
      class="absolute inset-0 bg-cover bg-center"
      style="background-image: url('{backgroundImage}'); transform: {parallaxTransform}"
    ></div>
    <div class="absolute inset-0 bg-black/50"></div>
  </div>
  
  <!-- Content -->
  <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-white">
    <div class="max-w-3xl">
      <h1 class="text-4xl md:text-6xl font-bold mb-6">
        {title}
      </h1>
      <p class="text-xl md:text-2xl mb-8 text-white/90">
        {subtitle}
      </p>
      <div class="flex flex-col sm:flex-row gap-4">
        <a 
          href="tel:{phoneNumber}"
          class="bg-blue-600 hover:bg-blue-700 text-white px-8 py-4 rounded-lg font-semibold transition-all duration-200 text-center"
        >
          Jetzt anrufen
        </a>
        <button 
          on:click={onContactClick}
          class="bg-white/20 hover:bg-white/30 backdrop-blur-sm text-white px-8 py-4 rounded-lg font-semibold transition-all duration-200"
        >
          Kostenloses Angebot
        </button>
      </div>
    </div>
  </div>
</section>