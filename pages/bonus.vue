<template>
  <div class="bg-white">
    <div class="fixed top-6 left-6 z-50">
      <nuxt-link to="/" class="flex items-center space-x-2 px-3 py-2 bg-white shadow-lg rounded text-gray-400 hover:text-gray-900">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M11 17l-5-5m0 0l5-5m-5 5h12" />
        </svg>
        Terug
      </nuxt-link>
    </div>

    <div v-if="showMobileMenu" class="relative z-40 lg:hidden" role="dialog" aria-modal="true">

      <div class="fixed inset-0 bg-black bg-opacity-25"></div>

      <div class="fixed inset-0 flex z-40">
        <div class="relative max-w-xs w-full bg-white shadow-xl pb-12 flex flex-col overflow-y-auto">
          <div class="px-4 pt-5 pb-2 flex">
            <button type="button" class="-m-2 p-2 rounded-md inline-flex items-center justify-center text-gray-400">
              <span class="sr-only">Close menu</span>
              <!-- Heroicon name: outline/x -->
              <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>
          </div>

          <!-- Links -->
          <div class="mt-2">
            <div class="border-b border-gray-200">
              <div class="-mb-px flex px-4 space-x-8" aria-orientation="horizontal" role="tablist">
                <!-- Selected: "text-gray-600 border-gray-600", Not Selected: "text-gray-900 border-transparent" -->
                <button id="tabs-1-tab-1" class="text-gray-900 border-transparent flex-1 whitespace-nowrap py-4 px-1 border-b-2 text-base font-medium" aria-controls="tabs-1-panel-1" role="tab" type="button">Wireframe Kits</button>

                <!-- Selected: "text-gray-600 border-gray-600", Not Selected: "text-gray-900 border-transparent" -->
                <button id="tabs-1-tab-2" class="text-gray-900 border-transparent flex-1 whitespace-nowrap py-4 px-1 border-b-2 text-base font-medium" aria-controls="tabs-1-panel-2" role="tab" type="button">Icons</button>
              </div>
            </div>

            <!-- 'Wireframe Kits' tab panel, show/hide based on tab state. -->
            <div id="tabs-1-panel-1" class="pt-10 pb-8 px-4 space-y-10" aria-labelledby="tabs-1-tab-1" role="tabpanel" tabindex="0">
              <div class="grid grid-cols-2 gap-x-4">
                <div class="group relative text-sm">
                  <div class="aspect-w-1 aspect-h-1 rounded-lg bg-gray-100 overflow-hidden group-hover:opacity-75">
                    <img src="https://tailwindui.com/img/ecommerce-images/product-page-05-menu-03.jpg" alt="Pricing page screenshot with tiered plan options and comparison table on colorful blue and green background." class="object-center object-cover">
                  </div>
                  <a href="#" class="mt-6 block font-medium text-gray-900">
                    <span class="absolute z-10 inset-0" aria-hidden="true"></span>
                    Scaffold
                  </a>
                  <p aria-hidden="true" class="mt-1">Shop now</p>
                </div>

                <div class="group relative text-sm">
                  <div class="aspect-w-1 aspect-h-1 rounded-lg bg-gray-100 overflow-hidden group-hover:opacity-75">
                    <img src="https://tailwindui.com/img/ecommerce-images/product-page-05-menu-04.jpg" alt="Application screenshot with tiered navigation and account settings form on color red and purple background." class="object-center object-cover">
                  </div>
                  <a href="#" class="mt-6 block font-medium text-gray-900">
                    <span class="absolute z-10 inset-0" aria-hidden="true"></span>
                    Bones
                  </a>
                  <p aria-hidden="true" class="mt-1">Shop now</p>
                </div>
              </div>

              <div>
                <p id="wireframe-application-heading-mobile" class="font-medium text-gray-900">Application UI</p>
                <ul role="list" aria-labelledby="wireframe-application-heading-mobile" class="mt-6 flex flex-col space-y-6">
                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Home Screens </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Detail Screens </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Settings Screens </a>
                  </li>
                </ul>
              </div>

              <div>
                <p id="wireframe-marketing-heading-mobile" class="font-medium text-gray-900">Marketing</p>
                <ul role="list" aria-labelledby="wireframe-marketing-heading-mobile" class="mt-6 flex flex-col space-y-6">
                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Landing Pages </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Pricing Pages </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Contact Pages </a>
                  </li>
                </ul>
              </div>

              <div>
                <p id="wireframe-ecommerce-heading-mobile" class="font-medium text-gray-900">Ecommerce</p>
                <ul role="list" aria-labelledby="wireframe-ecommerce-heading-mobile" class="mt-6 flex flex-col space-y-6">
                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Storefront Pages </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Product Pages </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Category Pages </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Shopping Cart Pages </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Checkout Pages </a>
                  </li>
                </ul>
              </div>
            </div>

            <!-- 'Icons' tab panel, show/hide based on tab state. -->
            <div id="tabs-1-panel-2" class="pt-10 pb-8 px-4 space-y-10" aria-labelledby="tabs-1-tab-2" role="tabpanel" tabindex="0">
              <div class="grid grid-cols-2 gap-x-4">
                <div class="group relative text-sm">
                  <div class="aspect-w-1 aspect-h-1 rounded-lg bg-gray-100 overflow-hidden group-hover:opacity-75">
                    <img src="https://tailwindui.com/img/ecommerce-images/product-page-05-menu-01.jpg" alt="Payment application dashboard screenshot with transaction table, financial highlights, and main clients on colorful purple background." class="object-center object-cover">
                  </div>
                  <a href="#" class="mt-6 block font-medium text-gray-900">
                    <span class="absolute z-10 inset-0" aria-hidden="true"></span>
                    Application UI Pack
                  </a>
                  <p aria-hidden="true" class="mt-1">Shop now</p>
                </div>

                <div class="group relative text-sm">
                  <div class="aspect-w-1 aspect-h-1 rounded-lg bg-gray-100 overflow-hidden group-hover:opacity-75">
                    <img src="https://tailwindui.com/img/ecommerce-images/product-page-05-menu-02.jpg" alt="Calendar user interface screenshot with icon buttons and orange-yellow theme." class="object-center object-cover">
                  </div>
                  <a href="#" class="mt-6 block font-medium text-gray-900">
                    <span class="absolute z-10 inset-0" aria-hidden="true"></span>
                    Marketing Icon Pack
                  </a>
                  <p aria-hidden="true" class="mt-1">Shop now</p>
                </div>
              </div>

              <div>
                <p id="icons-general-heading-mobile" class="font-medium text-gray-900">General Use</p>
                <ul role="list" aria-labelledby="icons-general-heading-mobile" class="mt-6 flex flex-col space-y-6">
                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Heroicons Solid </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Heroicons Outline </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Line Illustrations </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Hero Illustrations </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Branded Illustrations </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Skeuomorphic Illustrations </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Hand Drawn Illustrations </a>
                  </li>
                </ul>
              </div>

              <div>
                <p id="icons-application-heading-mobile" class="font-medium text-gray-900">Application UI</p>
                <ul role="list" aria-labelledby="icons-application-heading-mobile" class="mt-6 flex flex-col space-y-6">
                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Outlined </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Solid </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Branded </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Small </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Illustrations </a>
                  </li>
                </ul>
              </div>

              <div>
                <p id="icons-marketing-heading-mobile" class="font-medium text-gray-900">Marketing</p>
                <ul role="list" aria-labelledby="icons-marketing-heading-mobile" class="mt-6 flex flex-col space-y-6">
                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Outlined </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Solid </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Branded </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Small </a>
                  </li>

                  <li class="flow-root">
                    <a href="#" class="-m-2 p-2 block text-gray-500"> Illustrations </a>
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <div class="border-t border-gray-200 py-6 px-4 space-y-6">
            <div class="flow-root">
              <a href="#" class="-m-2 p-2 block font-medium text-gray-900">UI Kits</a>
            </div>

            <div class="flow-root">
              <a href="#" class="-m-2 p-2 block font-medium text-gray-900">Themes</a>
            </div>
          </div>

          <div class="border-t border-gray-200 py-6 px-4 space-y-6">
            <div class="flow-root">
              <a href="#" class="-m-2 p-2 block font-medium text-gray-900">Sign in</a>
            </div>
            <div class="flow-root">
              <a href="#" class="-m-2 p-2 block font-medium text-gray-900">Create account</a>
            </div>
          </div>

          <div class="border-t border-gray-200 py-6 px-4">
            <a href="#" class="-m-2 p-2 flex items-center">
              <img src="https://tailwindui.com/img/flags/flag-canada.svg" alt="" class="w-5 h-auto block flex-shrink-0">
              <span class="ml-3 block text-base font-medium text-gray-900"> CAD </span>
              <span class="sr-only">, change currency</span>
            </a>
          </div>
        </div>
      </div>
    </div>

    <TheHeader />

    <main class="mx-auto pt-14 pb-24 px-4 sm:pt-16 sm:pb-32 sm:px-6 lg:max-w-7xl lg:px-8">
      <!-- Product -->
      <div class="lg:grid lg:grid-rows-1 lg:grid-cols-7 lg:gap-x-8 lg:gap-y-10 xl:gap-x-16">
        <!-- Product image -->
        <div class="lg:row-end-1 lg:col-span-4">
          <div class="aspect-w-4 aspect-h-3 bg-gray-100 overflow-hidden">
            <img src="~/assets/images/sanghoon71-xQqGrdEi128-unsplash_compressed.jpeg" alt="Sample of 30 icons with friendly and fun details in outline, filled, and brand color styles." class="object-center object-cover">
          </div>
        </div>

        <!-- Product details -->
        <div class="max-w-2xl mx-auto mt-14 sm:mt-16 lg:max-w-none lg:mt-0 lg:row-end-2 lg:row-span-2 lg:col-span-3">
          <div class="flex flex-col-reverse">
            <div class="mt-4">
              <h1 class="text-2xl font-extrabold tracking-tight text-gray-900 sm:text-3xl">Electro Scooter</h1>

              <h2 id="information-heading" class="sr-only">Product informatie</h2>
              <p class="text-sm text-gray-500 mt-2">Versie 2.0</p>
            </div>

            <div>
              <h3 class="sr-only">Reviews</h3>
              <div class="flex items-center">
                <!--
                  Heroicon name: solid/star

                  Active: "text-yellow-400", Default: "text-gray-300"
                -->
                <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>

                <!-- Heroicon name: solid/star -->
                <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>

                <!-- Heroicon name: solid/star -->
                <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>

                <!-- Heroicon name: solid/star -->
                <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>

                <!-- Heroicon name: solid/star -->
                <svg class="text-gray-300 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>
              </div>
              <p class="sr-only">4 out of 5 stars</p>
            </div>
          </div>

          <p class="text-gray-500 mt-6">Reis duurzamer en sneller door de stad en bespaar jezelf het gedoe van openbaar vervoer.</p>

          <p class="m-0 text-xl font-semibold mt-6">
            €0,30/min
          </p>

          <div class="border-t border-gray-200 mt-10 pt-10">
            <h3 class="text font-semibold text-gray-900">Dynamic pricing</h3>
            <div class="mt-4 prose prose-sm text-gray-500">
              <p>
                Sinds februari 2020 maken wij gebruik van een nieuw prijsmodel, wat de beschikbaarheid van onze e-scooters vergroot. Op dit moment is dynamic pricing beschikbaar voor e-scooters in de steden: Eindhoven, Den Bosch, Delft, Groningen, Haarlem en Brussel.
              </p>
            </div>
          </div>

          <div class="border-t border-gray-200 mt-10 pt-10">
            <h3 class="text font-semibold text-gray-900">Gratis rijminuten</h3>
            <div class="mt-4 prose prose-sm text-gray-500">
              <p>
                Je krijgt 10 minuten bij je inschrijving en nog eens 10 minuten na je eerste rit.
              </p>
            </div>
          </div>

          <div class="border-t border-gray-200 mt-10 pt-10">
            <h3 class="text-sm font-medium text-gray-900">Share</h3>
            <ul role="list" class="flex items-center space-x-6 mt-4">
              <li>
                <a href="#" class="flex items-center justify-center w-6 h-6 text-gray-400 hover:text-gray-500">
                  <span class="sr-only">Share on Facebook</span>
                  <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20" aria-hidden="true">
                    <path fill-rule="evenodd" d="M20 10c0-5.523-4.477-10-10-10S0 4.477 0 10c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V10h2.54V7.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V10h2.773l-.443 2.89h-2.33v6.988C16.343 19.128 20 14.991 20 10z" clip-rule="evenodd" />
                  </svg>
                </a>
              </li>
              <li>
                <a href="#" class="flex items-center justify-center w-6 h-6 text-gray-400 hover:text-gray-500">
                  <span class="sr-only">Share on Instagram</span>
                  <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                    <path fill-rule="evenodd" d="M12.315 2c2.43 0 2.784.013 3.808.06 1.064.049 1.791.218 2.427.465a4.902 4.902 0 011.772 1.153 4.902 4.902 0 011.153 1.772c.247.636.416 1.363.465 2.427.048 1.067.06 1.407.06 4.123v.08c0 2.643-.012 2.987-.06 4.043-.049 1.064-.218 1.791-.465 2.427a4.902 4.902 0 01-1.153 1.772 4.902 4.902 0 01-1.772 1.153c-.636.247-1.363.416-2.427.465-1.067.048-1.407.06-4.123.06h-.08c-2.643 0-2.987-.012-4.043-.06-1.064-.049-1.791-.218-2.427-.465a4.902 4.902 0 01-1.772-1.153 4.902 4.902 0 01-1.153-1.772c-.247-.636-.416-1.363-.465-2.427-.047-1.024-.06-1.379-.06-3.808v-.63c0-2.43.013-2.784.06-3.808.049-1.064.218-1.791.465-2.427a4.902 4.902 0 011.153-1.772A4.902 4.902 0 015.45 2.525c.636-.247 1.363-.416 2.427-.465C8.901 2.013 9.256 2 11.685 2h.63zm-.081 1.802h-.468c-2.456 0-2.784.011-3.807.058-.975.045-1.504.207-1.857.344-.467.182-.8.398-1.15.748-.35.35-.566.683-.748 1.15-.137.353-.3.882-.344 1.857-.047 1.023-.058 1.351-.058 3.807v.468c0 2.456.011 2.784.058 3.807.045.975.207 1.504.344 1.857.182.466.399.8.748 1.15.35.35.683.566 1.15.748.353.137.882.3 1.857.344 1.054.048 1.37.058 4.041.058h.08c2.597 0 2.917-.01 3.96-.058.976-.045 1.505-.207 1.858-.344.466-.182.8-.398 1.15-.748.35-.35.566-.683.748-1.15.137-.353.3-.882.344-1.857.048-1.055.058-1.37.058-4.041v-.08c0-2.597-.01-2.917-.058-3.96-.045-.976-.207-1.505-.344-1.858a3.097 3.097 0 00-.748-1.15 3.098 3.098 0 00-1.15-.748c-.353-.137-.882-.3-1.857-.344-1.023-.047-1.351-.058-3.807-.058zM12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666zm5.338-3.205a1.2 1.2 0 110 2.4 1.2 1.2 0 010-2.4z" clip-rule="evenodd" />
                  </svg>
                </a>
              </li>
              <li>
                <a href="#" class="flex items-center justify-center w-6 h-6 text-gray-400 hover:text-gray-500">
                  <span class="sr-only">Share on Twitter</span>
                  <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20" aria-hidden="true">
                    <path d="M6.29 18.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0020 3.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.073 4.073 0 01.8 7.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 010 16.407a11.616 11.616 0 006.29 1.84" />
                  </svg>
                </a>
              </li>
            </ul>
          </div>
        </div>

        <div class="w-full max-w-2xl mx-auto mt-16 lg:max-w-none lg:mt-0 lg:col-span-4">
          <div>
            <div class="border-b border-gray-200">
              <div class="-mb-px flex space-x-8" aria-orientation="horizontal" role="tablist">
                <!-- Selected: "border-gray-600 text-gray-600", Not Selected: "border-transparent text-gray-700 hover:text-gray-800 hover:border-gray-300" -->
                <button id="tab-reviews" :class="['text-gray-700 hover:text-gray-800 whitespace-nowrap py-6 border-b-2 font-medium text-sm', tabs.current === 1 ? 'border-gray-500 hover: border-gray-500' : 'border-transparent hover:border-gray-300']" aria-controls="tab-panel-reviews" role="tab" type="button" @click="tabs.current = 1">Customer Reviews</button>
                <button id="tab-faq" :class="['text-gray-700 hover:text-gray-800 whitespace-nowrap py-6 border-b-2 font-medium text-sm', tabs.current === 2 ? 'border-gray-500 hover: border-gray-500' : 'border-transparent hover:border-gray-300']" aria-controls="tab-panel-faq" role="tab" type="button" @click="tabs.current = 2">FAQ</button>
                <button id="tab-license" :class="['text-gray-700 hover:text-gray-800 whitespace-nowrap py-6 border-b-2 font-medium text-sm', tabs.current === 3 ? 'border-gray-500 hover: border-gray-500' : 'border-transparent hover:border-gray-300']" aria-controls="tab-panel-license" role="tab" type="button" @click="tabs.current = 3">License</button>
              </div>
            </div>

            <!-- 'Customer Reviews' panel, show/hide based on tab state -->
            <div v-if="tabs.current === 1" id="tab-panel-reviews" class="-mb-10" aria-labelledby="tab-reviews" role="tabpanel" tabindex="0">
              <h3 class="sr-only">Customer Reviews</h3>

              <div class="flex text-sm text-gray-500 space-x-4">
                <div class="flex-none py-10">
                  <img src="https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=256&h=256&q=80" alt="" class="w-10 h-10 bg-gray-100 rounded-full">
                </div>
                <div class="flex-1 py-10">
                  <h3 class="font-medium text-gray-900">Emily Selman</h3>
                  <p><time datetime="2021-07-16">July 16, 2021</time></p>

                  <div class="flex items-center mt-4">
                    <!--
                      Heroicon name: solid/star

                      Active: "text-yellow-400", Default: "text-gray-300"
                    -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>

                    <!-- Heroicon name: solid/star -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>

                    <!-- Heroicon name: solid/star -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>

                    <!-- Heroicon name: solid/star -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>

                    <!-- Heroicon name: solid/star -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>
                  </div>
                  <p class="sr-only">5 out of 5 stars</p>

                  <div class="mt-4 prose prose-sm max-w-none text-gray-500">
                    <p>This icon pack is just what I need for my latest project. There's an icon for just about anything I could ever need. Love the playful look!</p>
                  </div>
                </div>
              </div>

              <div class="flex text-sm text-gray-500 space-x-4">
                <div class="flex-none py-10">
                  <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=256&h=256&q=80" alt="" class="w-10 h-10 bg-gray-100 rounded-full">
                </div>
                <div class="flex-1 py-10 border-t border-gray-200">
                  <h3 class="font-medium text-gray-900">Hector Gibbons</h3>
                  <p><time datetime="2021-07-12">July 12, 2021</time></p>

                  <div class="flex items-center mt-4">
                    <!--
                      Heroicon name: solid/star

                      Active: "text-yellow-400", Default: "text-gray-300"
                    -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>

                    <!-- Heroicon name: solid/star -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>

                    <!-- Heroicon name: solid/star -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>

                    <!-- Heroicon name: solid/star -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>

                    <!-- Heroicon name: solid/star -->
                    <svg class="text-yellow-400 h-5 w-5 flex-shrink-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>
                  </div>
                  <p class="sr-only">5 out of 5 stars</p>

                  <div class="mt-4 prose prose-sm max-w-none text-gray-500">
                    <p>Blown away by how polished this icon pack is. Everything looks so consistent and each SVG is optimized out of the box so I can use it directly with confidence. It would take me several hours to create a single icon this good, so it's a steal at this price.</p>
                  </div>
                </div>
              </div>

              <!-- More reviews... -->
            </div>

            <!-- 'FAQ' panel, show/hide based on tab state -->
            <div v-if="tabs.current === 2" id="tab-panel-faq" class="text-sm text-gray-500" aria-labelledby="tab-faq" role="tabpanel" tabindex="0">
              <h3 class="sr-only">Frequently Asked Questions</h3>

              <dl>
                <dt class="mt-10 font-medium text-gray-900">What format are these icons?</dt>
                <dd class="mt-2 prose prose-sm max-w-none text-gray-500">
                  <p>The icons are in SVG (Scalable Vector Graphic) format. They can be imported into your design tool of choice and used directly in code.</p>
                </dd>

                <dt class="mt-10 font-medium text-gray-900">Can I use the icons at different sizes?</dt>
                <dd class="mt-2 prose prose-sm max-w-none text-gray-500">
                  <p>Yes. The icons are drawn on a 24 x 24 pixel grid, but the icons can be scaled to different sizes as needed. We don&#039;t recommend going smaller than 20 x 20 or larger than 64 x 64 to retain legibility and visual balance.</p>
                </dd>

                <!-- More FAQs... -->
              </dl>
            </div>

            <!-- 'License' panel, show/hide based on tab state -->
            <div v-if="tabs.current === 3" id="tab-panel-license" class="pt-10" aria-labelledby="tab-license" role="tabpanel" tabindex="0">
              <h3 class="sr-only">License</h3>

              <div class="prose prose-sm max-w-none text-gray-500">
                <h4>Overview</h4>

                <p>For personal and professional use. You cannot resell or redistribute these icons in their original or modified state.</p>

                <ul role="list">
                  <li>You're allowed to use the icons in unlimited projects.</li>
                  <li>Attribution is not required to use the icons.</li>
                </ul>

                <h4>What you can do with it</h4>

                <ul role="list">
                  <li>Use them freely in your personal and professional work.</li>
                  <li>Make them your own. Change the colors to suit your project or brand.</li>
                </ul>

                <h4>What you can't do with it</h4>

                <ul role="list">
                  <li>Don't be greedy. Selling or distributing these icons in their original or modified state is prohibited.</li>
                  <li>Don't be evil. These icons cannot be used on websites or applications that promote illegal or immoral beliefs or activities.</li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>

    <div class="fixed bottom-0 left-0 right-0 border-gray-200 px-4 pb-4">
      <div class="flex items-end w-full h-full bg-white rounded-lg shadow-xl px-6 py-6">
        <div class="flex flex-1 items-center justify-evenly space-x-6 px-4 h-full mr-12">
          <InputNumber
            v-model="number"
            name="number"
            label="Aantal"
            :min="1"
            :max="9"
            class="w-full"
          />
          <InputDatePicker
            v-model="startDate"
            name="start-date"
            label="Start date"
            :options="startDateOptions"
            class="w-full"
          />
          <InputDatePicker
            v-model="endDate"
            name="end-date"
            label="End date"
            :options="endDateOptions"
            class="w-full"
          />
        </div>
        <button class="shrink-0 block px-3 py-2 rounded text-white bg-gray-900 px-6 font-semibold">
          Controleer beschikbaarheid
        </button>
      </div>
    </div>

    <TheFooter class="pb-32" />
  </div>
</template>
<script>
import { ref } from '@nuxtjs/composition-api';
import TheHeader from "@/components/organisms/TheHeader";
import TheFooter from "@/components/organisms/TheFooter";
import InputNumber from "@/components/atoms/InputNumber";
import InputDatePicker from "@/components/atoms/InputDatePicker";
import moment from "moment";
export default {
  name: 'ObjectDetailsPage',
  components: {
    TheHeader,
    TheFooter,
    InputNumber,
    InputDatePicker
  },
  setup() {
    const showMobileMenu = ref(false)
    const tabs = ref({
      current: 1
    })
    const object = ref({
      selected: {},
      options: [
        { value: 1, label: 'Millennium Falcon (YT-1300f)', description: 'YT-1300F light freighter' },
        { value: 2, label: 'Tantive IV', description: 'Corvette' },
        { value: 3, label: 'Lambda-class Imperial Shuttle', description: 'Multi-purpose transport' },
        { value: 4, label: 'X-wing', description: 'Space superiority fighter'},
      ]
    })

    const number = ref(1);
    const now = ref(new Date())
    const startDate = ref(now.value)
    const endDate = ref(null)
    const startDateOptions = ref({
      format: 'YYYY/MM/DD',
      minDate: moment().toDate(),
      maxDate: moment().add(32, 'days').toDate()
    })
    const endDateOptions = ref({
      format: 'YYYY/MM/DD',
      minDate: moment(new Date(startDate.value)).add(1, 'days').toDate(),
      maxDate: moment(new Date(startDate.value)).add(32, 'days').toDate()
    })

    return {
      showMobileMenu,
      tabs,
      number,
      object,
      startDate,
      endDate,
      startDateOptions,
      endDateOptions
    }
  }
}
</script>
