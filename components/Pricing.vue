<template>
  <section class="bg-white">
    <div class="py-8 px-4 mx-auto max-w-screen-xl text-center lg:py-16 lg:px-12">
      <h3 class="mb-4 text-xl font-bold tracking-tight leading-none text-black md:text-4xl lg:text-6x">
        Choose your plan</h3>
      <p class="my-12 text-lg font-normal text-black lg:text-xl sm:px-16 xl:px-48">Here at Flowbite
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quisquam neque soluta ducimus commodi dolorum facere
        aut magnam maiores, maxime numquam libero aliquid earum doloremque nulla excepturi beatae, iure natus.
        Exercitationem.</p>
      <div class="flex items-center justify-center mb-12">
        <div class="bg-gray-200 rounded-full overflow-hidden">
          <button id="weekly"
            class="toggle-button py-2 px-8 text-sm font-medium text-blue-500 focus:outline-none transition duration-200 ease-in-out bg-blue-950 rounded-full">Weekly</button>
          <button id="annually"
            class="toggle-button py-2 px-6 text-sm font-medium text-blue-500 focus:outline-none transition duration-200 ease-in-out rounded-full">Annually</button>
        </div>
      </div>
      <div class="flex flex-wrap justify-center gap-4">
        <PricingCard :plan="'Basic'" :price="29" />
        <PricingCard :plan="'Pro'" :price="49"/>
        <PricingCard :plan="'Premium'" :price="79" />
      </div>
    </div>
  </section>
</template>