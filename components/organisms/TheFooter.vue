<template>
  <footer aria-labelledby="footer-heading" class="bg-gray-50">
    <h2 id="footer-heading" class="sr-only">Footer</h2>
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="py-20 grid grid-cols-1 md:grid-cols-12 md:grid-flow-col md:gap-x-8 md:gap-y-16 md:auto-rows-min">
        <!-- Image section -->
        <div class="col-span-1 md:col-span-2 lg:row-start-1 lg:col-start-1">
          <NuxtLogo class="text-gray-800 h-8 w-auto" />
        </div>

        <!-- Sitemap sections -->
        <div class="mt-10 col-span-6 grid grid-cols-2 gap-8 sm:grid-cols-3 md:mt-0 md:row-start-1 md:col-start-3 md:col-span-8 lg:col-start-2 lg:col-span-6">
          <div class="grid grid-cols-1 gap-y-12 sm:col-span-2 sm:grid-cols-2 sm:gap-x-8">
            <div>
              <h3 class="text-sm font-medium text-gray-900">Products</h3>
              <ul role="list" class="mt-6 space-y-6">
                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> Wireframe Kits </a>
                </li>

                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> Icons </a>
                </li>

                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> UI Kits </a>
                </li>

                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> Themes </a>
                </li>
              </ul>
            </div>
            <div>
              <h3 class="text-sm font-medium text-gray-900">Company</h3>
              <ul role="list" class="mt-6 space-y-6">
                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> Who we are </a>
                </li>

                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> Open Source </a>
                </li>

                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> Press </a>
                </li>

                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> Careers </a>
                </li>

                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> License </a>
                </li>

                <li class="text-sm">
                  <a href="#" class="text-gray-500 hover:text-gray-600"> Privacy </a>
                </li>
              </ul>
            </div>
          </div>
          <div>
            <h3 class="text-sm font-medium text-gray-900">Customer Service</h3>
            <ul role="list" class="mt-6 space-y-6">
              <li class="text-sm">
                <a href="#" class="text-gray-500 hover:text-gray-600"> Chat </a>
              </li>

              <li class="text-sm">
                <a href="#" class="text-gray-500 hover:text-gray-600"> Contact </a>
              </li>

              <li class="text-sm">
                <a href="#" class="text-gray-500 hover:text-gray-600"> Secure Payments </a>
              </li>

              <li class="text-sm">
                <a href="#" class="text-gray-500 hover:text-gray-600"> FAQ </a>
              </li>
            </ul>
          </div>
        </div>

        <!-- Newsletter section -->
        <div class="mt-12 md:mt-0 md:row-start-2 md:col-start-3 md:col-span-8 lg:row-start-1 lg:col-start-9 lg:col-span-4">
          <h3 class="text-sm font-medium text-gray-900">Sign up for our newsletter</h3>
          <p class="mt-1 text-sm text-gray-500">Be the first to know when we release new products.</p>
          <form class="mt-3 sm:flex lg:block xl:flex">
            <label for="email-address" class="sr-only">Email address</label>
            <input id="email-address" type="text" autocomplete="email" required class="block w-full bg-white border border-gray-300 rounded-md shadow-sm py-2 px-4 text-base text-gray-900 placeholder-gray-500 focus:outline-none focus:border-indigo-500 focus:ring-1 focus:ring-indigo-500 sm:flex-1 sm:min-w-0 sm:max-w-xs lg:max-w-none">
            <div class="mt-4 sm:mt-0 sm:ml-4 sm:flex-shrink-0 lg:mt-4 lg:ml-0 xl:mt-0 xl:ml-4">
              <button type="submit" class="w-full bg-indigo-600 border border-transparent rounded-md shadow-sm py-2 px-4 flex items-center justify-center text-base font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">Sign up</button>
            </div>
          </form>
        </div>
      </div>

      <div class="border-t border-gray-200 py-10 text-center">
        <p class="text-sm text-gray-500">&copy; 2021 Clothing Company, Ltd.</p>
      </div>
    </div>
  </footer>
</template>
