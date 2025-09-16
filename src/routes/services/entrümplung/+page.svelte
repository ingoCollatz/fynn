<script lang="ts">
  import { onMount } from 'svelte';
  import ContactForm from '$lib/components/ContactForm.svelte';
  import ServiceHero from '$lib/components/services/ServiceHero.svelte';
  import ServiceDetails from '$lib/components/services/ServiceDetails.svelte';
  import ServicesOverview from '$lib/components/services/ServicesOverview.svelte';
  import ServiceCTA from '$lib/components/services/ServiceCTA.svelte';
  
  let scrollY = 0;
  let isMobile = false;
  
  onMount(() => {
    // Detect mobile devices
    isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent) || window.innerWidth < 768;
  });
  
  // Parallax transform calculation - disable on mobile to prevent stuttering
  $: parallaxTransform = isMobile ? 'translateY(0px)' : `translateY(${scrollY * 0.3}px)`;

  function scrollToContact() {
    const contactElement = document.getElementById('contact');
    if (contactElement) {
      const headerHeight = 80; // Account for fixed header height
      const elementPosition = contactElement.offsetTop - headerHeight;
      window.scrollTo({
        top: elementPosition,
        behavior: 'smooth'
      });
    }
  }

  // Service data
  const serviceFeatures = [
    {
      title: "Kostenlose Besichtigung",
      description: "Wir kommen vorbei und erstellen ein unverbindliches Angebot"
    },
    {
      title: "Fachgerechte Entsorgung",
      description: "Umweltgerechte Trennung und Entsorgung aller Materialien"
    },
    {
      title: "Schnelle Abwicklung",
      description: "Termine oft bereits am nächsten Tag möglich"
    },
    {
      title: "Faire Preise",
      description: "Transparente Kostenkalkulation ohne versteckte Gebühren"
    }
  ];

  const serviceTypes = [
    {
      title: "Haushaltsauflösung",
      description: "Komplette Wohnungsauflösung nach Todesfällen, Umzügen oder bei Wohnungswechsel. Wir übernehmen alles von A bis Z.",
      icon: '<path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z"/>',
      iconColor: "text-blue-600",
      iconBgColor: "bg-blue-100"
    },
    {
      title: "Kellerentrümplung",
      description: "Spezialisiert auf Keller und Dachböden. Auch schwer zugängliche Bereiche und große Mengen sind für uns kein Problem.",
      icon: '<path fill-rule="evenodd" d="M3 4a1 1 0 011-1h4a1 1 0 010 2H6.414l2.293 2.293a1 1 0 01-1.414 1.414L5 6.414V8a1 1 0 01-2 0V4zm9 1a1 1 0 010-2h4a1 1 0 011 1v4a1 1 0 01-2 0V6.414l-2.293 2.293a1 1 0 11-1.414-1.414L13.586 5H12zm-9 7a1 1 0 012 0v1.586l2.293-2.293a1 1 0 111.414 1.414L6.414 15H8a1 1 0 010 2H4a1 1 0 01-1-1v-4zm13-1a1 1 0 011 1v4a1 1 0 01-1 1h-4a1 1 0 010-2h1.586l-2.293-2.293a1 1 0 111.414-1.414L15.586 13H14a1 1 0 01-1-1z" clip-rule="evenodd"/>',
      iconColor: "text-green-600",
      iconBgColor: "bg-green-100"
    },
    {
      title: "Entsorgung",
      description: "Fachgerechte Trennung und umweltbewusste Entsorgung. Recycling und Spenden an gemeinnützige Organisationen inklusive.",
      icon: '<path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM8.707 7.293a1 1 0 00-1.414 1.414L8.586 10l-1.293 1.293a1 1 0 101.414 1.414L10 11.414l1.293 1.293a1 1 0 001.414-1.414L11.414 10l1.293-1.293a1 1 0 00-1.414-1.414L10 8.586 8.707 7.293z" clip-rule="evenodd"/>',
      iconColor: "text-purple-600",
      iconBgColor: "bg-purple-100"
    }
  ];
</script>

<svelte:window bind:scrollY={scrollY} />

<svelte:head>
  <title>Entrümplung - Professionelle Entrümpelung | Fynn Services</title>
  <meta name="description" content="Professionelle Entrümpelung von Häusern, Wohnungen, Kellern und Dachböden. Fachgerechte Entsorgung inklusive. Schnell, zuverlässig und fair." />
</svelte:head>



<ServiceHero 
  title="Professionelle Entrümplung"
  subtitle="Schnell, zuverlässig und umweltgerecht - wir räumen auf, damit Sie durchatmen können."
  backgroundImage="https://images.unsplash.com/photo-1610459716431-e07abcf74230?q=80&w=1515&auto=format"
  {parallaxTransform}
  onContactClick={scrollToContact}
/>

<ServiceDetails 
  title="Warum unsere Entrümplung?"
  description="Mit über 10 Jahren Erfahrung wissen wir, wie belastend eine Entrümplung sein kann. Deshalb übernehmen wir die komplette Abwicklung - von der Besichtigung bis zur fachgerechten Entsorgung."
  features={serviceFeatures}
  image="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=600&h=400&fit=crop&auto=format"
  imageAlt="Entrümplung Arbeitsplatz"
/>

<ServicesOverview 
  title="Unsere Entrümpelungs-Services"
  subtitle="Von der Haushaltsauflösung bis zur Kellerentrümplung - wir sind Ihr zuverlässiger Partner"
  services={serviceTypes}
/>

<ServiceCTA 
  title="Bereit für Ihre Entrümplung?"
  subtitle="Kontaktieren Sie uns noch heute für ein kostenloses und unverbindliches Angebot. Wir sind schnell vor Ort und kümmern uns um alles."
  onContactClick={scrollToContact}
/>

<!-- Contact Form -->
<ContactForm />

