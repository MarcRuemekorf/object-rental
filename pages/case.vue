<template>
  <div class="relative py-12">
    <div class="fixed top-6 left-6">
      <nuxt-link to="/" class="flex items-center space-x-2 px-3 py-2 bg-white shadow-lg rounded text-gray-400 hover:text-gray-900">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M11 17l-5-5m0 0l5-5m-5 5h12" />
        </svg>
        Terug
      </nuxt-link>
    </div>
    <div class="relative px-4 sm:px-6 lg:px-8">
      <div class="text-lg max-w-prose mx-auto">
        <h1 class="text-4xl font-semibild mb-12">
          Case
        </h1>
        <p class="mb-6">
          Bewoners van de gemeente Utrecht met een beperking komen in aanmerking voor een WMO-subsidie (Wet Maatschappelijke Ondersteuning). Dankzij deze subsidie kunnen bewoners tegen een beperkte vergoeding reizen met de ondersteuning die zij nodig hebben. Als een aanvraag wordt goedgekeurd door de gemeente dan ontvangt de bewoner een zogenaamde beschikking. Deze beschikking is een jaar geldig en wordt iedere jaar automatisch verlengd, tenzij de subsidie wordt stopgezet door de gemeente.
        </p>
        <p>
          Een beschikking heeft een budget, dit is het totale aantal kilometers dat de bewoner jaarlijks mag reizen zolang de beschikking actief is. Het budget wordt jaarlijks gereset zolang de beschikking actief is.
        </p>

        <!-- Aanvraag -->
        <h3 class="mt-12"><span class="bg-gray-100 text-gray-500 rounded-sm px-1">POST</span> /request</h3>
      </div>
    </div>
  </div>
</template>
