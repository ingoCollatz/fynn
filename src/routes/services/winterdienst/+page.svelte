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
      title: "24h Rufbereitschaft",
      description: "Bei Schneefall und Glatteis sind wir rund um die Uhr für Sie da"
    },
    {
      title: "Moderne Ausrüstung",
      description: "Professionelle Schneeräum- und Streufahrzeuge für alle Flächen"
    },
    {
      title: "Rechtssicherheit",
      description: "Erfüllung der Verkehrssicherungspflicht und Haftungsschutz"
    },
    {
      title: "Umweltschonend",
      description: "Verwendung von umweltfreundlichen Streumitteln wo möglich"
    }
  ];

  const serviceTypes = [
    {
      title: "Schneeräumung",
      description: "Professionelle Räumung von Gehwegen, Einfahrten, Parkplätzen und Zufahrten",
      icon: `<path d="M11.5,6V12.5L16,8L11.5,6M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M12,4A8,8 0 0,0 4,12A8,8 0 0,0 12,20A8,8 0 0,0 20,12A8,8 0 0,0 12,4Z"/>`,
      iconColor: "text-blue-600",
      iconBgColor: "bg-blue-100"
    },
    {
      title: "Streudienst",
      description: "Ausbringung von Streusalz und umweltfreundlichen Alternativen gegen Glatteis",
      icon: `<path d="M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M12,4.07C16.39,4.07 19.93,7.61 19.93,12C19.93,16.39 16.39,19.93 12,19.93C7.61,19.93 4.07,16.39 4.07,12C4.07,7.61 7.61,4.07 12,4.07Z"/>`,
      iconColor: "text-orange-600",
      iconBgColor: "bg-orange-100"
    },
    {
      title: "Wartungsservice",
      description: "Präventive Kontrollen und Wartung für eine optimale Wintervorbereitung",
      icon: `<path d="M12,15.5A3.5,3.5 0 0,1 8.5,12A3.5,3.5 0 0,1 12,8.5A3.5,3.5 0 0,1 15.5,12A3.5,3.5 0 0,1 12,15.5M19.43,12.97C19.47,12.65 19.5,12.33 19.5,12C19.5,11.67 19.47,11.34 19.43,11L21.54,9.37C21.73,9.22 21.78,8.95 21.66,8.73L19.66,5.27C19.54,5.05 19.27,4.97 19.05,5.05L16.56,6.05C16.04,5.66 15.5,5.32 14.87,5.07L14.5,2.42C14.46,2.18 14.25,2 14,2H10C9.75,2 9.54,2.18 9.5,2.42L9.13,5.07C8.5,5.32 7.96,5.66 7.44,6.05L4.95,5.05C4.73,4.96 4.46,5.05 4.34,5.27L2.34,8.73C2.21,8.95 2.27,9.22 2.46,9.37L4.57,11C4.53,11.34 4.5,11.67 4.5,12C4.5,12.33 4.53,12.65 4.57,12.97L2.46,14.63C2.27,14.78 2.21,15.05 2.34,15.27L4.34,18.73C4.46,18.95 4.73,19.03 4.95,18.95L7.44,17.94C7.96,18.34 8.5,18.68 9.13,18.93L9.5,21.58C9.54,21.82 9.75,22 10,22H14C14.25,22 14.46,21.82 14.5,21.58L14.87,18.93C15.5,18.68 16.04,18.34 16.56,17.94L19.05,18.95C19.27,19.04 19.54,18.95 19.66,18.73L21.66,15.27C21.78,15.05 21.73,14.78 21.54,14.63L19.43,12.97Z"/>`,
      iconColor: "text-green-600",
      iconBgColor: "bg-green-100"
    }
  ];
</script>

<svelte:window bind:scrollY />

<svelte:head>
  <title>Winterdienst - Professionelle Schneeräumung & Streudienst | Fynn</title>
  <meta name="description" content="Zuverlässiger Winterdienst mit 24h Bereitschaft. Schneeräumung, Streudienst und Wartung für sichere Wege im Winter." />
  <meta name="keywords" content="winterdienst, schneeräumung, streudienst, glatteis, verkehrssicherheit, räumdienst" />
</svelte:head>

<ServiceHero 
  title="Professioneller Winterdienst"
  subtitle="Sicher durch den Winter - Schneeräumung und Streudienst rund um die Uhr"
  backgroundImage="https://images.unsplash.com/photo-1579952363873-27d3bfad9c0d?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
  {parallaxTransform}
/>

<ServiceDetails 
  title="Warum unseren Winterdienst wählen?"
  description="Bei Schnee und Eis sorgen wir für sichere Wege. Mit modernen Räumfahrzeugen und umweltschonenden Streumitteln gewährleisten wir die Verkehrssicherheit auf Ihren Flächen - 24 Stunden am Tag."
  features={serviceFeatures}
  image="https://images.unsplash.com/photo-1547036967-23d11aacaee0?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80"
  imageAlt="Schneeräumung mit professioneller Ausrüstung"
/>

<ServicesOverview 
  title="Unsere Winterdienstleistungen"
  subtitle="Komplettservice für sichere Wege in der kalten Jahreszeit"
  services={serviceTypes}
/>

<ServiceCTA 
  title="Bereit für den Winter?"
  subtitle="Sichern Sie sich jetzt unseren Winterdienst und sorgen Sie für verkehrssichere Wege"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
/>


<ContactForm />
