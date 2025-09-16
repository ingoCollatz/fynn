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
      title: "Ganzjährige Betreuung",
      description: "Professionelle Gartenpflege in allen Jahreszeiten"
    },
    {
      title: "Fachkundiges Personal",
      description: "Erfahrene Gärtner mit umfassendem Pflanzenwissen"
    },
    {
      title: "Moderne Geräte",
      description: "Professionelle Gartengeräte für optimale Ergebnisse"
    },
    {
      title: "Individuelle Betreuung",
      description: "Maßgeschneiderte Pflegepläne für jeden Garten"
    }
  ];

  const serviceTypes = [
    {
      title: "Rasenpflege",
      description: "Mähen, Düngen, Vertikutieren und Nachsaat für einen perfekten Rasen",
      icon: `<path d="M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M12,20C7.59,20 4,16.41 4,12C4,7.59 7.59,4 12,4C16.41,4 20,7.59 20,12C20,16.41 16.41,20 12,20Z"/>`,
      iconColor: "text-green-600",
      iconBgColor: "bg-green-100"
    },
    {
      title: "Heckenschnitt",
      description: "Fachgerechter Schnitt von Hecken und Sträuchern für gesundes Wachstum",
      icon: `<path d="M11,2V8H9V11H11V22H13V11H15V8H13V2H11M5,12V14H8V12H5M16,12V14H19V12H16Z"/>`,
      iconColor: "text-blue-600",
      iconBgColor: "bg-blue-100"
    },
    {
      title: "Beetpflege",
      description: "Bepflanzung, Unkrautbekämpfung und saisonale Gestaltung Ihrer Beete",
      icon: `<path d="M6.05,8.05C6.05,7.5 6.5,7.05 7.05,7.05C7.6,7.05 8.05,7.5 8.05,8.05C8.05,8.6 7.6,9.05 7.05,9.05C6.5,9.05 6.05,8.6 6.05,8.05M12,2L11.5,8.05L17.45,8.55L16.95,14.6L11,14.1L11.5,20.15L5.55,19.65L6.05,13.6L0.1,14.1L0.6,8.05L6.55,8.55L6.05,2.5"/>`,
      iconColor: "text-purple-600",
      iconBgColor: "bg-purple-100"
    }
  ];
</script>

<svelte:window bind:scrollY />

<svelte:head>
  <title>Gartenpflege - Professionelle Gartenbetreuung | Fynn</title>
  <meta name="description" content="Professionelle Gartenpflege das ganze Jahr über. Rasenpflege, Heckenschnitt und Beetpflege von erfahrenen Gärtnern." />
  <meta name="keywords" content="gartenpflege, rasenpflege, heckenschnitt, beetpflege, gartenservice, gärtner" />
</svelte:head>

<ServiceHero 
  title="Professionelle Gartenpflege"
  subtitle="Ihr Garten in besten Händen - das ganze Jahr über gepflegt und schön"
  backgroundImage="https://images.unsplash.com/photo-1416879595882-3373a0480b5b?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
  {parallaxTransform}
/>

<ServiceDetails 
  title="Warum unsere Gartenpflege wählen?"
  description="Ein gepflegter Garten ist eine Oase der Entspannung. Unsere erfahrenen Gärtner kümmern sich um alle Aspekte der Gartenpflege - von der Rasenpflege bis zur Beetgestaltung, damit Sie Ihren Garten einfach nur genießen können."
  features={serviceFeatures}
  image="https://images.unsplash.com/photo-1586771107445-d3ca888129ff?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80"
  imageAlt="Professionelle Gartenpflege in Aktion"
/>

<ServicesOverview 
  title="Unsere Gartenpflegeleistungen"
  subtitle="Umfassende Betreuung für einen Garten, der das ganze Jahr über schön aussieht"
  services={serviceTypes}
/>

<ServiceCTA 
  title="Bereit für einen perfekten Garten?"
  subtitle="Lassen Sie uns gemeinsam Ihren Traumgarten verwirklichen und pflegen"
  phoneNumber="+49123456789"
  onContactClick={scrollToContact}
/>


<ContactForm />
