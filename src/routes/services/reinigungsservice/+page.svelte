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
      title: "Professionelle Ausrüstung",
      description: "Moderne Reinigungsgeräte und umweltfreundliche Reinigungsmittel"
    },
    {
      title: "Flexible Termine",
      description: "Regelmäßige oder einmalige Reinigung nach Ihren Wünschen"
    },
    {
      title: "Geschultes Personal",
      description: "Erfahrene Reinigungskräfte mit hohen Qualitätsstandards"
    },
    {
      title: "Alle Bereiche",
      description: "Büros, Praxen, Wohnungen und Gewerbeflächen"
    }
  ];

  const serviceTypes = [
    {
      title: "Büroreinigung",
      description: "Regelmäßige oder einmalige Reinigung von Büroräumen, Empfangsbereichen und Besprechungsräumen",
      icon: `<path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>`,
      iconColor: "text-blue-600",
      iconBgColor: "bg-blue-100"
    },
    {
      title: "Praxisreinigung",
      description: "Hygienische Reinigung von Arztpraxen, Kliniken und medizinischen Einrichtungen",
      icon: `<path d="M19 8l-4 4h3c0 3.31-2.69 6-6 6-1.01 0-1.97-.25-2.8-.7l-1.46 1.46C8.97 19.54 10.43 20 12 20c4.42 0 8-3.58 8-8h3l-4-4zM6 12c0-3.31 2.69-6 6-6 1.01 0 1.97.25 2.8.7l1.46-1.46C15.03 4.46 13.57 4 12 4c-4.42 0-8 3.58-8 8H1l4 4 4-4H6z"/>`,
      iconColor: "text-green-600",
      iconBgColor: "bg-green-100"
    },
    {
      title: "Wohnungsreinigung",
      description: "Gründliche Reinigung von Privatwohnungen, Ein- und Auszug oder regelmäßige Pflege",
      icon: `<path d="M10 20v-6h4v6h5v-8h3L12 3 2 12h3v8z"/>`,
      iconColor: "text-purple-600",
      iconBgColor: "bg-purple-100"
    }
  ];
</script>

<svelte:window bind:scrollY />

<svelte:head>
  <title>Reinigungsservice - Professionelle Reinigung | Fynn</title>
  <meta name="description" content="Professioneller Reinigungsservice für Büros, Praxen und Wohnungen. Flexible Termine, geschultes Personal und umweltfreundliche Reinigungsmittel." />
  <meta name="keywords" content="reinigungsservice, büroreinigung, praxisreinigung, wohnungsreinigung, professionell" />
</svelte:head>

<ServiceHero 
  title="Professioneller Reinigungsservice"
  subtitle="Saubere Räume für Ihr Wohlbefinden - von Büros bis Wohnungen"
  backgroundImage="https://images.unsplash.com/photo-1581578731548-c64695cc6952?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
  {parallaxTransform}
/>

<ServiceDetails 
  title="Warum unseren Reinigungsservice wählen?"
  description="Wir bieten professionelle Reinigungsdienstleistungen für alle Bereiche. Mit modernen Geräten und umweltfreundlichen Reinigungsmitteln sorgen wir für hygienische Sauberkeit in Ihren Räumen."
  features={serviceFeatures}
  image="https://images.unsplash.com/photo-1527515637462-cff94eecc1ac?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80"
  imageAlt="Professionelle Reinigungskraft bei der Arbeit"
/>

<ServicesOverview 
  title="Unsere Reinigungsleistungen"
  subtitle="Von der Büroreinigung bis zur Wohnungsreinigung - wir bieten maßgeschneiderte Lösungen"
  services={serviceTypes}
/>

<ServiceCTA 
  title="Bereit für saubere Räume?"
  subtitle="Kontaktieren Sie uns für ein kostenloses Beratungsgespräch und individuelles Angebot"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
/>


<ContactForm />
