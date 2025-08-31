<script>
  const services = [
    { icon: "🛠️", title: "Reparaturen", desc: "Schnelle Hilfe bei kleinen und großen Schäden." },
    { icon: "🏠", title: "Renovierungen", desc: "Professionelle Renovierungen für Ihr Zuhause." },
    { icon: "🪚", title: "Möbelmontage", desc: "Aufbau und Montage von Möbeln und Küchen." },
    { icon: "🌳", title: "Gartenarbeit", desc: "Pflege und Gestaltung von Gärten und Grünanlagen." },
    { icon: "🚿", title: "Bad & Küche", desc: "Installationen und Reparaturen im Sanitärbereich." },
    { icon: "🔧", title: "Kleine Elektroarbeiten", desc: "Installation von Lampen, Steckdosen uvm." }
  ];
</script>

<section id="services" class="py-16 px-6 bg-gray-50 scroll-mt-20">
  <h2 class="text-3xl font-bold text-center mb-10">Unsere Leistungen</h2>
  <div class="grid gap-8 md:grid-cols-3 max-w-6xl mx-auto">
    {#each services as s}
      <div class="bg-white p-6 rounded-2xl shadow text-center hover:shadow-lg transition-shadow">
        <div class="text-4xl mb-4">{s.icon}</div>
        <h3 class="text-xl font-semibold mb-2">{s.title}</h3>
        <p class="text-gray-600">{s.desc}</p>
      </div>
    {/each}
  </div>
  <div class="text-center mt-12">
    <a href="#contact" class="bg-blue-600 text-white px-8 py-3 rounded-lg font-semibold hover:bg-blue-700 transition-colors">
      Kostenvoranschlag anfordern
    </a>
  </div>
</section>
