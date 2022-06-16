<template>
  <div class="h-screen">
    <div class="fixed top-6 left-6">
      <nuxt-link to="/" class="flex items-center space-x-2 px-3 py-2 bg-white shadow-lg rounded text-gray-400 hover:text-gray-900">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M11 17l-5-5m0 0l5-5m-5 5h12" />
        </svg>
        Terug
      </nuxt-link>
    </div>
    <div class="flex flex-col h-full space-y-6 px-4 sm:px-6 lg:px-8 py-6">
      <header class="flex items-center justify-center shrink-0 bg-gray-100 border-2 border-indigo-800 text-lg p-6">
        Header
      </header>
      <div class="flex-1">
        <div class="grid grid-cols-3 gap-3 md:gap-6">
          <main class="col-span-3 md:col-span-2 flex items-center justify-center h-80 bg-gray-100 border-2 border-indigo-800 text-lg p-6">
            Content
          </main>
          <aside class="col-span-3 md:col-span-1 flex items-center justify-center h-80 bg-gray-100 border-2 border-indigo-800 text-lg p-6">
            Sidebar
          </aside>
        </div>
      </div>
      <div class="flex items-center justify-center shrink-0 bg-gray-100 border-2 border-indigo-800 text-lg p-6">
        Footer
      </div>
    </div>
  </div>
</template>
