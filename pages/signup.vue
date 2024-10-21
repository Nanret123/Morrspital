<template>
  <div class="flex justify-center items-center min-h-screen">
    <div class="flex w-full max-w-4xl shadow-lg">
      <div class="w-1/2 bg-blue-500 text-white">
        Left Section
      </div>
      <div>
        <div class="flex flex-col items-center justify-center px-6 py-5 mx-auto lg:py-0">
          <div class="w-full md:mt-0 sm:max-w-md xl:p-0">
            <div class="space-y-4 md:space-y-6">
              <h1 class="text-xl font-bold leading-tight tracking-tight text-gray-900 md:text-2xl">
                Sign up to Morrspital
              </h1>
              <form class="space-y-4 md:space-y-6" action="#">
                <div>
                  <label for="firstName" class="block mb-2 text-sm font-medium text-gray-900">first name </label>
                  <input type="firstName" name="firstName" id="firstName"
                    class="bg-gray-50 border border-gray-300 text-gray-900 rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                    placeholder="John" required>
                </div>
                <div>
                  <label for="lastName" class="block mb-2 text-sm font-medium text-gray-900">last name</label>
                  <input type="lastName" name="lastName" id="lastName"
                    class="bg-gray-50 border border-gray-300 text-gray-900 rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                    placeholder="Doe" required>
                </div>
                <div>
                  <label for="email" class="block mb-2 text-sm font-medium text-gray-900">Your
                    email</label>
                  <input type="email" name="email" id="email"
                    class="bg-gray-50 border border-gray-300 text-gray-900 rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                    placeholder="name@company.com" required>
                </div>
                <div>
                  <label for="password" class="block mb-2 text-sm font-medium text-gray-900">Password</label>
                  <input type="password" name="password" id="password" placeholder="••••••••"
                    class="bg-gray-50 border border-gray-300 text-gray-900 rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                    required>
                </div>
                <div class="flex items-center justify-between">
                  <div class="flex items-start">
                    <div class="flex items-center h-5">
                      <input id="remember" aria-describedby="remember" type="checkbox"
                        class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-primary"
                        required>
                    </div>
                    <div class="ml-2 mr-3 text-sm">
                      <label for="remember" class="text-gray-500">Remember me</label>
                    </div>
                  </div>
                  <a href="#" class="text-sm font-medium text-primary-600 hover:underline">Forgot
                    password?</a>
                </div>
                <button type="submit"
                  class="w-full bg-purple-900 font-medium rounded-lg text-sm px-5 py-2.5 text-center">Sign
                  up</button>
                <p class="text-sm font-light text-gray-500">
                  Already have an account? <a href="#" class="font-medium text-primary-600 hover:underline">Sign
                    in</a>
                </p>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>