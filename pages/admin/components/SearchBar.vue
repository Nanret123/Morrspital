<template>
  <div class="h-[90px] flex items-center justify-between px-10 py-0">
    <h4 class="font-bold text-3xl">Dashboard</h4>

    <form class="max-w-md mx-auto">
      <label for="default-search" class="mb-2 text-sm font-medium text-gray-900 sr-only">Search</label>
      <div class="relative w-[500px]">
        <div class="absolute inset-y-0 start-0 flex items-center ps-3 pointer-events-none">
          <svg class="w-4 h-4 text-gray-500 dark:text-gray-400" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
            fill="none" viewBox="0 0 20 20">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z" />
          </svg>
        </div>
        <input type="search" id="default-search"
          class="block w-full p-2 ps-10 text-sm text-gray-900 border border-gray-300 rounded-lg bg-gray-50 focus:ring-blue-500 focus:border-blue-500 outline-none"
          placeholder="Search Here..." required />
        <button type="submit"
          class="text-white absolute end-2.5 bottom-0.5 right-0 bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-4 py-2 ">Search</button>
      </div>
    </form>
    <div class="flex items-center">
      <div class="bg-amber-50 px-[10px] py-[5px] rounded-sm">
        <Icon name="bx:bell" style="color: #FFA412" class="text-xl" />
      </div>
      <img src="/images/spongebob.png" class="h-10 w-10 rounded-full mx-3" />
      <div class="flex flex-col">
        <span>Victor John</span>
        <span>Oncologist</span>
      </div>

      
    </div>
  </div>
</template>