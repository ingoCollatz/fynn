<script lang="ts">
  import { onMount } from 'svelte';
  import Header from '$lib/components/Header.svelte';
  import Footer from '$lib/components/Footer.svelte';

  onMount(() => {
    // Set page title
    document.title = 'Datenschutz - Fynn Schomann Hausmeisterservice & Gartenpflege';
  });
</script>

<svelte:head>
  <title>Datenschutz - Fynn Schomann Hausmeisterservice & Gartenpflege</title>
  <meta name="description" content="Datenschutzerklärung von Fynn Schomann Hausmeisterservice & Gartenpflege" />
</svelte:head>

<Header />

<main class="min-h-screen bg-white py-20">
  <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
    <!-- Header -->
    <div class="mb-12">
      <h1 class="text-3xl font-bold text-gray-900 mb-4">Datenschutzerklärung</h1>
      <p class="text-lg text-gray-600">Schutz Ihrer persönlichen Daten</p>
    </div>

    <!-- Content -->
    <div class="space-y-8">
      
      <!-- Allgemeine Hinweise -->
      <section class="mb-8">
        <h2 class="text-xl font-bold text-gray-900 mb-4">Allgemeine Hinweise</h2>
        <div class="text-gray-700 space-y-4">
          <p>
            Die folgenden Hinweise geben einen einfachen Überblick darüber, was mit Ihren personenbezogenen 
            Daten passiert, wenn Sie diese Website besuchen. Personenbezogene Daten sind alle Daten, mit 
            denen Sie persönlich identifiziert werden können.
          </p>
          <p>
            Ausführliche Informationen zum Thema Datenschutz entnehmen Sie unserer unter diesem Text 
            aufgeführten Datenschutzerklärung.
          </p>
        </div>
      </section>

      <!-- Datenerfassung -->
      <section class="mb-8">
        <h2 class="text-xl font-bold text-gray-900 mb-4">Datenerfassung auf dieser Website</h2>
        
        <div class="space-y-6">
          <div>
            <h3 class="text-lg font-semibold text-gray-900 mb-3">Wer ist verantwortlich für die Datenerfassung?</h3>
            <p class="text-gray-700 mb-3">
              Die Datenverarbeitung auf dieser Website erfolgt durch den Websitebetreiber:
            </p>
            <div class="space-y-1">
              <p><strong>Fynn Schomann</strong></p>
              <p>Hausmeisterservice & Gartenpflege</p>
              <p>Musterstraße 123</p>
              <p>60311 Frankfurt am Main</p>
              <p>Telefon: +49 123 456 789</p>
              <p>E-Mail: info@fynn-schomann.de</p>
            </div>
          </div>

          <div>
            <h3 class="text-lg font-semibold text-gray-900 mb-3">Wie erfassen wir Ihre Daten?</h3>
            <p class="text-gray-700">
              Ihre Daten werden zum einen dadurch erhoben, dass Sie uns diese mitteilen. Hierbei kann es sich 
              z.B. um Daten handeln, die Sie in ein Kontaktformular eingeben oder uns per E-Mail oder Telefon 
              übermitteln.
            </p>
          </div>
        </div>
      </section>

      <!-- Ihre Rechte -->
      <section class="mb-8">
        <h2 class="text-xl font-bold text-gray-900 mb-4">Ihre Rechte</h2>
        <div class="space-y-4">
          <div>
            <h3 class="font-semibold text-gray-900 mb-2">Auskunftsrecht</h3>
            <p class="text-gray-700">
              Sie haben jederzeit das Recht, unentgeltlich Auskunft über Herkunft, Empfänger und 
              Zweck Ihrer gespeicherten personenbezogenen Daten zu erhalten.
            </p>
          </div>
          <div>
            <h3 class="font-semibold text-gray-900 mb-2">Recht auf Berichtigung</h3>
            <p class="text-gray-700">
              Sie haben ein Recht auf Berichtigung unrichtiger oder auf Vervollständigung 
              richtiger Daten.
            </p>
          </div>
          <div>
            <h3 class="font-semibold text-gray-900 mb-2">Recht auf Löschung</h3>
            <p class="text-gray-700">
              Sie haben das Recht, Ihre gespeicherten personenbezogenen Daten löschen zu lassen, 
              soweit nicht die Verarbeitung zur Ausübung des Rechts auf freie Meinungsäußerung erforderlich ist.
            </p>
          </div>
          <div>
            <h3 class="font-semibold text-gray-900 mb-2">Widerspruchsrecht</h3>
            <p class="text-gray-700">
              Sie haben das Recht, der künftigen Verarbeitung Ihrer personenbezogenen Daten 
              zu widersprechen.
            </p>
          </div>
        </div>
      </section>

      <!-- Kontaktformular -->
      <section class="mb-8">
        <h2 class="text-xl font-bold text-gray-900 mb-4">Kontaktformular</h2>
        <div class="text-gray-700 space-y-4">
          <p>
            Wenn Sie uns per Kontaktformular Anfragen zukommen lassen, werden Ihre Angaben aus dem 
            Anfrageformular inklusive der von Ihnen dort angegebenen Kontaktdaten zwecks Bearbeitung 
            der Anfrage und für den Fall von Anschlussfragen bei uns gespeichert.
          </p>
          <p>
            Diese Daten geben wir nicht ohne Ihre Einwilligung weiter. Die Verarbeitung der in das 
            Kontaktformular eingegebenen Daten erfolgt ausschließlich auf Grundlage Ihrer Einwilligung 
            (Art. 6 Abs. 1 lit. a DSGVO).
          </p>
          <div class="mt-4">
            <p class="font-semibold text-gray-900">Zweck der Datenverarbeitung:</p>
            <ul class="mt-2 space-y-1">
              <li>• Bearbeitung Ihrer Anfrage</li>
              <li>• Kontaktaufnahme für Rückfragen</li>
              <li>• Angebotserstellung</li>
              <li>• Terminvereinbarung</li>
            </ul>
          </div>
        </div>
      </section>

      <!-- Server-Log-Dateien -->
      <section class="mb-8">
        <h2 class="text-xl font-bold text-gray-900 mb-4">Server-Log-Dateien</h2>
        <div class="text-gray-700 space-y-4">
          <p>
            Der Provider der Seiten erhebt und speichert automatisch Informationen in so genannten 
            Server-Log-Dateien, die Ihr Browser automatisch an uns übermittelt:
          </p>
          <ul class="space-y-1">
            <li>• Browsertyp und Browserversion</li>
            <li>• Verwendetes Betriebssystem</li>
            <li>• Referrer URL</li>
            <li>• Hostname des zugreifenden Rechners</li>
            <li>• Uhrzeit der Serveranfrage</li>
            <li>• IP-Adresse</li>
          </ul>
          <p>
            Eine Zusammenführung dieser Daten mit anderen Datenquellen wird nicht vorgenommen. 
            Die Erfassung dieser Daten erfolgt auf Grundlage von Art. 6 Abs. 1 lit. f DSGVO.
          </p>
        </div>
      </section>

      <!-- WhatsApp -->
      <section class="mb-8">
        <h2 class="text-xl font-bold text-gray-900 mb-4">WhatsApp Business</h2>
        <div class="text-gray-700 space-y-4">
          <p>
            Wir nutzen WhatsApp Business für die Kommunikation mit unseren Kunden. Anbieter ist die 
            Meta Platforms Ireland Limited, 4 Grand Canal Square, Grand Canal Harbour, Dublin 2, Irland.
          </p>
          <p>
            Wenn Sie uns über WhatsApp kontaktieren, werden Ihre Daten (Telefonnummer, Nachrichten, 
            Medien) von WhatsApp verarbeitet. Details finden Sie in der Datenschutzerklärung von WhatsApp.
          </p>
          <div class="mt-4">
            <p class="font-semibold mb-2">Rechtsgrundlage:</p>
            <p>Die Verarbeitung erfolgt auf Grundlage Ihrer Einwilligung (Art. 6 Abs. 1 lit. a DSGVO).</p>
          </div>
        </div>
      </section>

      <!-- Speicherdauer -->
      <section class="mb-8">
        <h2 class="text-xl font-bold text-gray-900 mb-4">Speicherdauer</h2>
        <div class="text-gray-700">
          <p>
            Ihre Daten werden nur so lange gespeichert, wie dies zur Erfüllung des jeweiligen 
            Zwecks erforderlich ist oder gesetzliche Aufbewahrungsfristen bestehen. Nach Wegfall 
            des jeweiligen Zwecks bzw. Ablauf dieser Fristen werden die entsprechenden Daten 
            routinemäßig gelöscht.
          </p>
        </div>
      </section>

      <!-- Kontakt bei Datenschutz -->
      <div class="border-t border-gray-300 pt-6 text-center">
        <h3 class="font-semibold text-lg mb-3">Fragen zum Datenschutz?</h3>
        <p class="mb-4">Bei Fragen zur Erhebung, Verarbeitung oder Nutzung Ihrer personenbezogenen Daten kontaktieren Sie uns:</p>
        <div class="space-y-1">
          <p class="font-semibold">E-Mail: info@fynn-schomann.de</p>
          <p>Telefon: +49 123 456 789</p>
        </div>
      </div>

    </div>

    <!-- Back to Home -->
    <div class="text-center mt-12">
      <a 
        href="/" 
        class="text-blue-600 hover:text-blue-800 underline"
      >
        ← Zurück zur Startseite
      </a>
    </div>

  </div>
</main>

<Footer />