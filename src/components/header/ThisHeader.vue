<!-- eslint-disable vuejs-accessibility/mouse-events-have-key-events -->
<template>
  <header class="bg-white relative">
    <p class="lg:px-8 sm:px-6 text-white font-medium text-sm px-4 bg-indigo-600 items-center justify-center flex h-10">
      Frete grátis em compras acima de R$100</p>
    <nav class="lg:px-8 sm:px-6 px-4 border-b border-gray-200">
      <div class="max-w-7xl mx-auto">
        <div class="flex items-center h-16">
          <button type="button" class="lg:hidden text-gray-400 p-2 bg-white rounded-md relative">
            <span class="inset[-0.125rem] relativesolute"></span>
            <span class="sr-only">Open menu</span>
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
              stroke="currentColor" class="w-6 h-6">
              <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5">
              </path>
            </svg>
          </button>
          <div class="lg:ml-0 flex ml-4">
            <a href="#">
              <span class="sr-only">Company name</span>
              <img class="w-auto h-8" src="https://tailwindui.com/img/logos/mark.svg?color=indigo&amp;shade=600" alt="">
            </a>
          </div>
          <div class="lg:self-stretch lg:block lg:ml-8 hidden">
            <div class="h-full flex odd:space-x-8">
              <div class="flex" @mouseleave="closeWomanMenu()">
                <div class="relative flex">
                  <button @mouseenter="openWomanMenu()"
                    :class="woman_menu.open ? 'border-indigo-600 text-indigo-600' : 'border-transparent text-gray-700'"
                    class="ease-out duration-200 transition font-medium text-sm pt-px border-b-2 items-center flex -mb-px z-10 relative"
                    type="button">Feminino</button>
                </div>
                <ThisMenu :open="woman_menu.open" :items="woman_menu.data" />
              </div>
              <div class="flex" @mouseleave="closeManMenu()">
                <div class="relative flex">
                  <button @mouseenter="openManMenu()"
                    :class="man_menu.open ? 'border-indigo-600 text-indigo-600' : 'border-transparent text-gray-700'"
                    class="ease-out duration-200 transition font-medium text-sm pt-px border-b-2 items-center flex -mb-px z-10 relative"
                    type="button">Masculino</button>
                </div>
                <ThisMenu :open="man_menu.open" :items="man_menu.data" />
              </div>
              <a href="#" class="flex items-center text-sm font-medium text-gray-700">Company</a>
              <a href="#" class="flex items-center text-sm font-medium text-gray-700">Stores</a>
            </div>
          </div>
          <div class="flex items-center ml-auto">
            <div class="lg:justify-end lg:items-center lg:flex-1 lg:flex hidden odd:space-x-6">
              <a href="#" class="text-gray-700 font-medium text-sm">Sign in</a>
              <span class="bg-gray-200 w-px h-6"></span>
              <a href="#" class="text-gray-700 font-medium text-sm">Create account</a>
            </div>
            <div class="lg:ml-6 flex">
              <a href="#" class="text-gray-400 p-2">
                <span class="sr-only">Search</span>
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                  stroke="currentColor" class="w-6 h-6">
                  <path stroke-linecap="round" stroke-linejoin="round"
                    d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"></path>
                </svg>
              </a>
            </div>
            <div class="lg:ml-6 flow-root ml-4">
              <a href="#" class="flex items-center -m-2 p-2">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                  stroke="currentColor" class="text-gray-400 shrink-0 w-6 h-6">
                  <path stroke-linecap="round" stroke-linejoin="round"
                    d="M15.75 10.5V6a3.75 3.75 0 10-7.5 0v4.5m11.356-1.993l1.263 12c.07.665-.45 1.243-1.119 1.243H4.25a1.125 1.125 0 01-1.12-1.243l1.264-12A1.125 1.125 0 015.513 7.5h12.974c.576 0 1.059.435 1.119 1.007zM8.625 10.5a.375.375 0 11-.75 0 .375.375 0 01.75 0zm7.5 0a.375.375 0 11-.75 0 .375.375 0 01.75 0z">
                  </path>
                </svg>
                <span class="text-gray-700 font-medium text-sm ml-2">0</span>
                <span class="sr-only">items in cart, view bag</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
import ThisMenu from './ThisMenu.vue';

export default {
  components: {
    ThisMenu,
  },
  data() {
    return {
      woman_menu: {
        open: false,
        data: {
          clothes: ['Tops', 'Dresses', 'Pants', 'Denim', 'Sweaters', 'T-Shirts', 'Jackets', 'Activewear', 'Browse All'],
          accessories: ['Watches', 'Wallets', 'Bags', 'Sunglasses', 'Hats', 'T-Belts'],
          brands: ['Full Nelson', 'My Way', 'Re-Arranged', 'Counterfeit', 'Significant Other'],
          campaigns: [{
            title: 'New Arrivals',
            img: 'https://tailwindui.com/img/ecommerce-images/mega-menu-category-01.jpg',
            alt: 'Models sitting back to back, wearing Basic Tee in black and bone.',
          }, {
            title: 'Basic Tees',
            img: 'https://tailwindui.com/img/ecommerce-images/mega-menu-category-02.jpg',
            alt: 'Close up of Basic Tee fall bundle with off-white, ochre, olive, and black tees.',
          }],
        },
      },
      man_menu: {
        open: false,
        data: {
          clothes: ['Tops', 'Pants', 'Sweaters', 'T-Shirts', 'Jackets', 'Activewear', 'Browse All'],
          accessories: ['Watches', 'Wallets', 'Bags', 'Sunglasses', 'Hats', 'Belts'],
          brands: ['Re-Arranged', 'Counterfeit', 'Full Nelson', 'My Way'],
          campaigns: [{
            title: 'New Arrivals',
            img: 'https://tailwindui.com/img/ecommerce-images/product-page-04-detail-product-shot-01.jpg',
            alt: 'Drawstring top with elastic loop closure and textured interior padding.',
          }, {
            title: 'Artwork Tees',
            img: 'https://tailwindui.com/img/ecommerce-images/category-page-02-image-card-06.jpg',
            alt: 'Three shirts in gray, white, and blue arranged on table with same line drawing of hands and shapes overlapping on front of shirt.',
          }],
        },
      },
    };
  },
  methods: {
    openWomanMenu() {
      this.woman_menu.open = true;
    },
    closeWomanMenu() {
      this.woman_menu.open = false;
    },
    openManMenu() {
      this.man_menu.open = true;
    },
    closeManMenu() {
      this.man_menu.open = false;
    },
  },
};
</script>
