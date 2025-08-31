<script>
  const projects = [
    {
      title: "Badezimmer Renovierung",
      description: "Komplette Badsanierung in Frankfurt-Sachsenhausen",
      image: "🛁",
      category: "Renovierung"
    },
    {
      title: "Küchenmontage",
      description: "Aufbau einer modernen Einbauküche",
      image: "🏠",
      category: "Montage"
    },
    {
      title: "Gartenpflege",
      description: "Gartengestaltung und Heckenschnitt",
      image: "🌳",
      category: "Garten"
    },
    {
      title: "Elektroinstallation",
      description: "Installation neuer Steckdosen und Beleuchtung",
      image: "💡",
      category: "Elektro"
    },
    {
      title: "Möbelaufbau",
      description: "Aufbau von Schlafzimmermöbeln",
      image: "🪚",
      category: "Montage"
    },
    {
      title: "Reparaturarbeiten",
      description: "Diverses Handwerk im Wohnbereich",
      image: "🔧",
      category: "Reparatur"
    }
  ];
</script>

<section id="portfolio" class="py-16 px-6 bg-white scroll-mt-20">
  <h2 class="text-3xl font-bold text-center mb-10">Unsere Arbeiten</h2>
  <p class="text-center text-gray-600 mb-12 max-w-2xl mx-auto">
    Ein Einblick in unsere erfolgreich abgeschlossenen Projekte. 
    Qualität und Zufriedenheit stehen bei uns an erster Stelle.
  </p>
  
  <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3 max-w-6xl mx-auto">
    {#each projects as project}
      <div class="bg-gray-50 rounded-2xl overflow-hidden shadow hover:shadow-lg transition-shadow">
        <div class="bg-blue-600 text-white p-8 text-center">
          <div class="text-6xl mb-4">{project.image}</div>
        </div>
        <div class="p-6">
          <span class="inline-block bg-blue-100 text-blue-600 px-3 py-1 rounded-full text-sm font-medium mb-2">
            {project.category}
          </span>
          <h3 class="font-semibold text-lg mb-2">{project.title}</h3>
          <p class="text-gray-600 text-sm">{project.description}</p>
        </div>
      </div>
    {/each}
  </div>
  
  <div class="text-center mt-12">
    <p class="text-gray-600 mb-4">Haben Sie ein ähnliches Projekt?</p>
    <a href="#contact" class="bg-yellow-400 text-black px-8 py-3 rounded-lg font-semibold hover:bg-yellow-300 transition-colors">
      Projekt besprechen
    </a>
  </div>
</section>
