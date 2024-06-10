<template>
  <Transition>
    <div v-if="open" class="text-gray-500 text-sm z-10 top-full inset-x-0 absolute max-w-7xl mx-auto shadow"
      style="--button-width: 50.328125px;">
      <div class="bg-white top-1/2 inset-0 absolute"></div>
      <div class="bg-white relative">
        <div class="lg:px-8 sm:px-6 px-4">
          <div class="py-16 gap-y-10 gap-x-8 grid grid-cols-2 ">
            <div class="gap-x-8 grid grid-cols-2 col-start-2">
              <div v-for="campaign in items.campaigns" class="sm:text-sm text-base relative group">
                <div
                  class="bg-gray-100 rounded-lg overflow-hidden group-hover:opacity-75 aspect-h-1 aspect-w-1 relative">
                  <img :src="campaign.img" :alt="campaign.alt" class="object-center object-cover">
                </div>
                <a href="#" class="text-gray-900 font-medium block mt-6">
                  <span class="z-10 inset-0 absolute"></span>
                  {{ campaign.title }}
                </a>
                <p class="mt-1">Shop now</p>
              </div>
            </div>
            <div class="text-sm gap-x-10 gap-y-10 grid grid-cols-3 row-start-1">
              <div>
                <p class="text-gray-900 font-medium">Clothing</p>
                <ul class="sm:mt-4 mt-6 sm:even:space-y-4 even:space-y-6">
                  <li v-for="Clothing in items.clothes" class="flex">
                    <a href="#" class="hover:text-gray-800">{{ Clothing }}</a>
                  </li>
                </ul>
              </div>
              <div>
                <p class="text-gray-900 font-medium">Accessories</p>
                <ul class="sm:mt-4 mt-6 sm:even:space-y-4 even:space-y-6">
                  <li v-for="accessory in items.accessories" class="flex">
                    <a href="#" class="hover:text-gray-800">{{ accessory }}</a>
                  </li>
                </ul>
              </div>
              <div>
                <p class="text-gray-900 font-medium">Brands</p>
                <ul class="sm:mt-4 mt-6 sm:even:space-y-4 even:space-y-6">
                  <li v-for="brand in items.brands" class="flex">
                    <a href="#" class="hover:text-gray-800">{{ brand }}</a>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </Transition>
</template>

<script>
export default {
  props: {
    open: Boolean,
    items: Object,
  },
};
</script>

<style>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
