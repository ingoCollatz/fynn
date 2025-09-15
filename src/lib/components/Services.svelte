<script>
  const services = [
    { 
      icon: "�️", 
      title: "Entrümplung", 
      desc: "Professionelle Entrümpelung von Häusern, Wohnungen, Kellern und Dachböden. Fachgerechte Entsorgung inklusive.",
      features: ["Haushaltsauflösungen", "Kellerentrümplung", "Entsorgung inklusive"]
    },
    { 
      icon: "✨", 
      title: "Außen- & Innenreinigung", 
      desc: "Gründliche Reinigung von Gebäuden innen und außen. Von der Glasreinigung bis zur Tiefenreinigung.",
      features: ["Fassadenreinigung", "Fensterreinigung", "Grundreinigung"]
    },
    { 
      icon: "🔧", 
      title: "Hausmeisterservice", 
      desc: "Umfassende Betreuung und Wartung Ihrer Immobilie. Regelmäßige Kontrollen und schnelle Reparaturen.",
      features: ["Objektbetreuung", "Wartungsarbeiten", "Kleinreparaturen"]
    },
    { 
      icon: "❄️", 
      title: "Winterdienst", 
      desc: "Zuverlässiger Räum- und Streudienst in der kalten Jahreszeit. Pünktlich und verkehrssicher.",
      features: ["Schneeräumung", "Streudienst", "Eisentfernung"]
    },
    { 
      icon: "🏗️", 
      title: "Einbau von Fertigbauteilen", 
      desc: "Fachgerechte Montage und Installation von Fertigbauteilen. Präzise Arbeit mit professionellem Werkzeug.",
      features: ["Montagearbeiten", "Installationen", "Anschlussarbeiten"]
    }
  ];

  function scrollToContact() {
    const contactElement = document.getElementById('contact');
    if (contactElement) {
      contactElement.scrollIntoView({ behavior: 'smooth' });
    }
  }
</script>

<section id="services" class="py-20 bg-white">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <!-- Section Header -->
    <div class="text-center mb-16">
      <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
        Unsere Leistungen
      </h2>
      <p class="text-xl text-gray-600 max-w-3xl mx-auto">
        Professionelle Dienstleistungen für Ihr Zuhause und Ihre Immobilie. 
        Zuverlässig, sauber und fair – darauf können Sie sich verlassen.
      </p>
    </div>

    <!-- Services Grid -->
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
      {#each services as service}
        <div class="group bg-white border border-gray-100 rounded-2xl p-8 hover:shadow-xl transition-all duration-300 hover:-translate-y-1">
          <!-- Icon -->
          <div class="flex items-center justify-center w-16 h-16 bg-gradient-to-br from-blue-500 to-purple-600 rounded-2xl mb-6 group-hover:scale-110 transition-transform duration-300">
            <span class="text-2xl">{service.icon}</span>
          </div>
          
          <!-- Content -->
          <h3 class="text-2xl font-bold text-gray-900 mb-4">{service.title}</h3>
          <p class="text-gray-600 mb-6 leading-relaxed">{service.desc}</p>
          
          <!-- Features -->
          <ul class="space-y-2">
            {#each service.features as feature}
              <li class="flex items-center text-sm text-gray-500">
                <div class="w-1.5 h-1.5 bg-blue-500 rounded-full mr-3"></div>
                {feature}
              </li>
            {/each}
          </ul>
        </div>
      {/each}
    </div>

    <!-- Call to Action -->
    <div class="text-center bg-gradient-to-r from-blue-600 to-purple-600 rounded-3xl p-12">
      <h3 class="text-3xl font-bold text-white mb-4">
        Bereit für professionellen Service?
      </h3>
      <p class="text-blue-100 text-lg mb-8 max-w-2xl mx-auto">
        Kontaktieren Sie uns noch heute für eine kostenlose Beratung und ein unverbindliches Angebot.
      </p>
      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <button 
          class="bg-white text-blue-600 px-8 py-4 rounded-lg font-semibold hover:bg-gray-100 transition-colors"
          on:click={scrollToContact}
        >
          Kostenlose Beratung
        </button>
        <a 
          href="tel:+49123456789" 
          class="bg-blue-700 text-white px-8 py-4 rounded-lg font-semibold hover:bg-blue-800 transition-colors"
        >
          📞 Sofort anrufen
        </a>
      </div>
    </div>
  </div>
</section>
