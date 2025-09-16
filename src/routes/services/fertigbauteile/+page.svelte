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
      title: "Fachgerechter Einbau",
      description: "Professionelle Montage durch erfahrene Handwerker und Spezialisten"
    },
    {
      title: "Qualitätsgarantie",
      description: "Nur hochwertige Fertigbauteile von namhaften Herstellern"
    },
    {
      title: "Zeitersparnis",
      description: "Schnelle Installation dank vorgefertigter Bauteile"
    },
    {
      title: "Komplettservice",
      description: "Von der Planung bis zur finalen Abnahme alles aus einer Hand"
    }
  ];

  const serviceTypes = [
    {
      title: "Fertiggaragen",
      description: "Einbau von Beton- und Stahlfertiggaragen in verschiedenen Größen und Ausführungen",
      icon: `<path d="M10 20v-6h4v6h5v-8h3L12 3 2 12h3v8z"/>`,
      iconColor: "text-gray-600",
      iconBgColor: "bg-gray-100"
    },
    {
      title: "Fertigkeller",
      description: "Montage von vorgefertigten Kellerelementen und kompletten Fertigkellern",
      icon: `<path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>`,
      iconColor: "text-blue-600",
      iconBgColor: "bg-blue-100"
    },
    {
      title: "Fertigtreppen",
      description: "Installation von Betonfertigtreppen für Innen- und Außenbereiche",
      icon: `<path d="M2 21h2v-2h2v-2h2v-2h2v-2h2v-2h2v-2h2v-2h2v-2h2V7h2V5h2V3H10v2H8v2H6v2H4v2H2v10z"/>`,
      iconColor: "text-green-600",
      iconBgColor: "bg-green-100"
    }
  ];
</script>

<svelte:window bind:scrollY />

<svelte:head>
  <title>Einbau von Fertigbauteilen - Professionelle Montage | Fynn</title>
  <meta name="description" content="Fachgerechter Einbau von Fertigbauteilen. Fertiggaragen, Fertigkeller und Fertigtreppen - Komplettservice von der Planung bis zur Montage." />
  <meta name="keywords" content="fertigbauteile, fertiggarage, fertigkeller, fertigtreppen, einbau, montage, betonfertigteile" />
</svelte:head>

<ServiceHero 
  title="Einbau von Fertigbauteilen"
  subtitle="Professionelle Montage für schnelle und qualitätsvolle Baulösungen"
  backgroundImage="https://images.unsplash.com/photo-1541976590-713941681591?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
  {parallaxTransform}
/>

<ServiceDetails 
  title="Warum Fertigbauteile von uns einbauen lassen?"
  description="Fertigbauteile bieten eine schnelle und kosteneffiziente Lösung für verschiedene Bauprojekte. Wir sorgen für den fachgerechten Einbau und die ordnungsgemäße Installation aller Fertigbauteile."
  features={serviceFeatures}
  image="https://images.unsplash.com/photo-1504307651254-35680f356dfd?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80"
  imageAlt="Professioneller Einbau von Fertigbauteilen"
/>

<ServicesOverview 
  title="Unsere Fertigbauteil-Services"
  subtitle="Hochwertige Fertigbauteile für alle Bereiche - fachgerecht installiert"
  services={serviceTypes}
/>

<ServiceCTA 
  title="Ihr Bauprojekt mit Fertigbauteilen?"
  subtitle="Lassen Sie uns gemeinsam die beste Lösung für Ihr Bauvorhaben finden"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
/>

<ContactForm />
