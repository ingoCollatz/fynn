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
      title: "24/7 Bereitschaft",
      description: "Rund um die Uhr erreichbar für Notfälle und dringende Reparaturen"
    },
    {
      title: "Umfassende Betreuung",
      description: "Von kleinen Reparaturen bis zur kompletten Gebäudewartung"
    },
    {
      title: "Erfahrene Handwerker",
      description: "Qualifizierte Fachkräfte für alle Bereiche der Haustechnik"
    },
    {
      title: "Kostenoptimierung",
      description: "Regelmäßige Wartung verhindert teure Reparaturen"
    }
  ];

  const serviceTypes = [
    {
      title: "Technische Wartung",
      description: "Regelmäßige Überprüfung und Wartung von Heizung, Lüftung, Sanitär und Elektrik",
      icon: `<path d="M22.7 19l-9.1-9.1c.9-2.3.4-5-1.5-6.9-2-2-5-2.4-7.4-1.3L9 6 6 9 1.6 4.7C.4 7.1.9 10.1 2.9 12.1c1.9 1.9 4.6 2.4 6.9 1.5l9.1 9.1c.4.4 1 .4 1.4 0l2.3-2.3c.5-.4.5-1.1.1-1.4z"/>`,
      iconColor: "text-orange-600",
      iconBgColor: "bg-orange-100"
    },
    {
      title: "Kleinreparaturen",
      description: "Schnelle Behebung von defekten Wasserhähnen, Türen, Fenstern und mehr",
      icon: `<path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>`,
      iconColor: "text-blue-600",
      iconBgColor: "bg-blue-100"
    },
    {
      title: "Objektbetreuung",
      description: "Komplette Betreuung von Wohn- und Gewerbeimmobilien mit regelmäßigen Kontrollen",
      icon: `<path d="M10 20v-6h4v6h5v-8h3L12 3 2 12h3v8z"/>`,
      iconColor: "text-green-600",
      iconBgColor: "bg-green-100"
    }
  ];
</script>

<svelte:window bind:scrollY />

<svelte:head>
  <title>Hausmeisterservice - Professionelle Gebäudebetreuung | Fynn</title>
  <meta name="description" content="Zuverlässiger Hausmeisterservice mit 24/7 Bereitschaft. Technische Wartung, Kleinreparaturen und komplette Objektbetreuung für Ihre Immobilie." />
  <meta name="keywords" content="hausmeisterservice, gebäudebetreuung, wartung, reparaturen, haustechnik, objektbetreuung" />
</svelte:head>

<ServiceHero 
  title="Zuverlässiger Hausmeisterservice"
  subtitle="Professionelle Betreuung Ihrer Immobilie - rund um die Uhr für Sie da"
  backgroundImage="https://images.unsplash.com/photo-1621905251189-08b45d6a269e?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
  {parallaxTransform}
/>

<ServiceDetails 
  title="Warum unseren Hausmeisterservice wählen?"
  description="Wir kümmern uns um die komplette Betreuung Ihrer Immobilie. Von der präventiven Wartung bis zu Notfallreparaturen - wir sind Ihr zuverlässiger Partner für alle Belange rund um Ihr Gebäude."
  features={serviceFeatures}
  image="https://images.unsplash.com/photo-1504307651254-35680f356dfd?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80"
  imageAlt="Hausmeister bei Wartungsarbeiten"
/>

<ServicesOverview 
  title="Unsere Hausmeisterleistungen"
  subtitle="Umfassende Gebäudebetreuung für Wohn- und Gewerbeimmobilien"
  services={serviceTypes}
/>

<ServiceCTA 
  title="Ihre Immobilie in besten Händen?"
  subtitle="Kontaktieren Sie uns für eine professionelle Beratung zu unserem Hausmeisterservice"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
/>


<ContactForm />
