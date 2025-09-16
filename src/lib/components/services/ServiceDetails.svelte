<script lang="ts">
  export let title: string;
  export let description: string;
  export let features: Array<{title: string, description: string}>;
  export let image: string;
  export let imageAlt: string;
</script>

<section class="py-20 bg-white">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="grid lg:grid-cols-2 gap-12 items-center">
      <!-- Content -->
      <div>
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-6">
          {title}
        </h2>
        <p class="text-lg text-gray-600 mb-8">
          {description}
        </p>
        
        <div class="space-y-4">
          {#each features as feature}
            <div class="flex items-start space-x-3">
              <div class="w-6 h-6 bg-blue-100 rounded-full flex items-center justify-center flex-shrink-0 mt-1">
                <svg class="w-4 h-4 text-blue-600" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/>
                </svg>
              </div>
              <div>
                <h3 class="font-semibold text-gray-900">{feature.title}</h3>
                <p class="text-gray-600">{feature.description}</p>
              </div>
            </div>
          {/each}
        </div>
      </div>
      
      <!-- Image -->
      <div class="relative">
        <img 
          src={image}
          alt={imageAlt}
          class="rounded-2xl shadow-2xl"
        />
        <div class="absolute -bottom-6 -left-6 w-32 h-32 bg-blue-100 rounded-full opacity-20"></div>
        <div class="absolute -top-6 -right-6 w-24 h-24 bg-green-100 rounded-full opacity-30"></div>
      </div>
    </div>
  </div>
</section>