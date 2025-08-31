<script>
  const testimonials = [
    { name: "Frau Schneider", text: "Sehr zuverlässig und freundlich. Die Arbeit wurde sauber und schnell erledigt." },
    { name: "Herr Müller", text: "Top Preis-Leistungs-Verhältnis. Ich kann den Service nur weiterempfehlen!" },
    { name: "Familie Becker", text: "Unsere Küche wurde perfekt aufgebaut. Vielen Dank!" }
  ];
</script>

<section id="testimonials" class="py-16 px-6 bg-gray-50 scroll-mt-20">
  <h2 class="text-3xl font-bold text-center mb-10">Kundenstimmen</h2>
  <div class="grid gap-8 md:grid-cols-3 max-w-6xl mx-auto">
    {#each testimonials as t}
      <div class="bg-white p-6 rounded-2xl shadow hover:shadow-lg transition-shadow">
        <div class="text-yellow-400 text-xl mb-3">★★★★★</div>
        <p class="italic text-gray-700 mb-4">"{t.text}"</p>
        <span class="font-semibold text-blue-600">– {t.name}</span>
      </div>
    {/each}
  </div>
  <div class="text-center mt-10">
    <p class="text-gray-600 mb-4">Werden Sie unser nächster zufriedener Kunde!</p>
    <a href="#contact" class="bg-blue-600 text-white px-6 py-3 rounded-lg font-semibold hover:bg-blue-700 transition-colors">
      Jetzt Termin vereinbaren
    </a>
  </div>
</section>
