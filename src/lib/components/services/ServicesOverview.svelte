<script lang="ts">
  export let title: string;
  export let subtitle: string;
  export let backgroundImage: string = '';
  export let services: Array<{
    title: string;
    description: string;
    icon: string;
    iconColor: string;
    iconBgColor: string;
  }>;
</script>

<section 
  class="relative py-20 bg-white bg-cover bg-center bg-no-repeat"
  style={backgroundImage ? `background-image: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('${backgroundImage}')` : ''}
>
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">
        {title}
      </h2>
      <p class="text-xl text-gray-600 max-w-3xl mx-auto">
        {subtitle}
      </p>
    </div>
    
    <div class="grid md:grid-cols-3 gap-8">
      {#each services as service}
        <div class="bg-white rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow duration-300">
          <div class="w-16 h-16 {service.iconBgColor} rounded-2xl flex items-center justify-center mb-6">
            <svg class="w-8 h-8 {service.iconColor}" fill="currentColor" viewBox="0 0 20 20">
              {@html service.icon}
            </svg>
          </div>
          <h3 class="text-xl font-bold text-gray-900 mb-4">{service.title}</h3>
          <p class="text-gray-600">
            {service.description}
          </p>
        </div>
      {/each}
    </div>
  </div>
</section>