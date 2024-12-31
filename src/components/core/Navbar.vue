<template>
  <div :class="[
      'fixed z-20 w-full px-6 pt-6 xl:px-28 md:px-10 transition-transform duration-300',
      isVisible ? 'translate-y-0' : '-translate-y-full',
      showMenu ? 'h-full ' : 'h-fit',
    ]">
    <!-- Navbar -->
    <div 
      :class="[
          showMenu ? 'bg-stone-900 text-white dark:bg-white dark:text-stone-900' : 'bg-white/20 dark:bg-stone-500/30 backdrop-blur-md',
          showMenu ? 'rounded-3xl ' : 'rounded-full',
          'shadow-md',
          'bg-blur-lg',
          'transition-colors ease-in-out duration-500'
      ]"
    >
      <div class="flex relative flex-row justify-between items-center px-4 py-2.5 w-full md:py-3.5 text-stone-900 sm:flex-row dark:text-white">
        <!-- Logo -->
        <div class="flex justify-between items-center w-full">
          <div class="inline-flex items-center space-x-3.5 group">
            <RouterLink to="/" class="">
              <div class="flex relative items-center group">
                <!-- Logo -->
                <div class="z-10">
                  <!-- Light -->
                  <svg 
                  class="block dark:hidden" 
                  xmlns="http://www.w3.org/2000/svg" width="46" height="40" fill="none" viewBox="0 0 46 40">
                    <path fill="#fff" d="M45.919 24.287c0 9.907-6.96 15.713-22.96 15.713S0 34.194 0 24.287C0 14.381 8.323 6.565 22.96 6.565c14.636 0 22.959 7.816 22.959 17.722Z"/>
                    <path fill="#E1DED8" d="M5.225 6.076c-.06-1.469 1.63-2.332 2.785-1.424l4.932 3.878c.36.284.475.774.204 1.144-.465.633-1.375 1.61-2.972 2.423-1.603.817-3 1.014-3.836 1.043-.481.018-.841-.374-.86-.855l-.253-6.21Zm35.512-.287c.06-1.469-1.63-2.332-2.785-1.424L33.02 8.243c-.36.284-.476.774-.204 1.144.465.633 1.374 1.61 2.972 2.423 1.603.817 2.999 1.013 3.836 1.043.48.018.84-.374.86-.855l.253-6.21Z"/>
                    <mask id="a" fill="#fff">
                      <path fill-rule="evenodd" d="M5.015 5.572c.024-1.377 1.575-2.17 2.706-1.383l5.417 3.771c2.852-.9 6.137-1.395 9.821-1.395 3.672 0 6.947.492 9.793 1.386l5.404-3.762c1.13-.787 2.681.006 2.705 1.383l.12 6.923a.84.84 0 0 1-.007.142c3.234 3.098 4.945 7.16 4.945 11.65 0 9.907-6.96 15.713-22.96 15.713S0 34.194 0 24.287c0-4.474 1.698-8.521 4.908-11.615a.997.997 0 0 1-.013-.177l.12-6.923Z" clip-rule="evenodd"/>
                    </mask>
                    <path fill="#E1DED8" d="m7.72 4.189.763-1.095L7.72 4.19ZM5.016 5.572l1.333.023-1.333-.023Zm8.123 2.388-.762 1.094.538.375.625-.197-.4-1.272Zm19.614-.01-.4 1.273.624.196.537-.374-.761-1.094Zm5.404-3.761-.762-1.095.762 1.095Zm2.705 1.383-1.333.023 1.333-.023Zm.12 6.923 1.334-.023-1.333.023Zm-.007.142-1.323-.166-.083.665.484.463.922-.962Zm-36.066.035.925.96.503-.484-.112-.69-1.316.214Zm-.013-.177-1.333-.023 1.333.023Zm3.588-9.4c-2.006-1.397-4.758.01-4.8 2.454l2.665.046a.389.389 0 0 1 .611-.312l1.524-2.189Zm5.417 3.77-5.417-3.77L6.96 5.283l5.417 3.771L13.9 6.866Zm9.06-1.633c-3.804 0-7.225.511-10.223 1.456l.802 2.544c2.707-.854 5.854-1.333 9.42-1.333V5.232ZM33.15 6.68c-2.99-.94-6.402-1.447-10.192-1.447V7.9c3.554 0 6.693.476 9.393 1.324l.799-2.544Zm4.243-3.585L31.99 6.857l1.523 2.188 5.405-3.762-1.524-2.189Zm4.8 2.455c-.042-2.444-2.794-3.851-4.8-2.455l1.524 2.189a.389.389 0 0 1 .61.312l2.666-.046Zm.12 6.923-.12-6.923-2.666.046.12 6.923 2.667-.046Zm-.017.33c.014-.109.02-.22.018-.33l-2.666.046c0-.015 0-.03.002-.047l2.646.33Zm4.955 11.485c0-4.85-1.855-9.26-5.355-12.613L40.051 13.6c2.967 2.843 4.533 6.555 4.533 10.688h2.667ZM22.959 41.333c8.122 0 14.191-1.466 18.259-4.392 4.147-2.983 6.034-7.35 6.034-12.654h-2.667c0 4.602-1.592 8.092-4.925 10.49-3.412 2.453-8.823 3.89-16.7 3.89v2.666ZM-1.333 24.287c0 5.304 1.887 9.671 6.034 12.654 4.068 2.925 10.136 4.392 18.258 4.392v-2.666c-7.877 0-13.288-1.437-16.7-3.89-3.333-2.398-4.926-5.888-4.926-10.49h-2.666Zm5.315-12.575c-3.474 3.349-5.315 7.745-5.315 12.575h2.666c0-4.117 1.555-7.816 4.5-10.655l-1.85-1.92Zm-.42.76c-.003.14.007.278.03.414l2.632-.427a.335.335 0 0 1 .004.06l-2.666-.047Zm.12-6.923-.12 6.923 2.666.046.12-6.923-2.666-.046Z" mask="url(#a)"/>
                    <ellipse cx="22.959" cy="24.574" fill="#E1DED8" rx="12.628" ry="8.968"/>
                    <circle cx="15.498" cy="23.211" r="1.435" fill="#1C1917"/>
                    <circle cx="30.565" cy="23.211" r="1.435" fill="#1C1917"/>
                    <ellipse cx="22.959" cy="25.579" fill="#1C1917" rx="1.435" ry=".933"/>
                    <path stroke="#A8A29E" stroke-width=".717" d="M0-.359h3.129" transform="matrix(.94 .34117 -.36763 .92997 9.184 26.511)"/>
                    <path stroke="#A8A29E" stroke-width=".717" d="M0-.359h3.129" transform="matrix(.94 -.34117 -.36763 -.92997 9.184 30.099)"/>
                    <path stroke="#A8A29E" stroke-width=".717" d="M0-.359h3.129" transform="matrix(-.94 .34117 .36763 .92997 36.592 26.511)"/>
                    <path stroke="#A8A29E" stroke-width=".717" d="M0-.359h3.129" transform="matrix(-.94 -.34117 .36763 -.92997 36.592 30.099)"/>
                  </svg>
                  <!-- Dark -->
                  <svg 
                  class="hidden dark:block" 
                  xmlns="http://www.w3.org/2000/svg" width="46" height="40" fill="none" viewBox="0 0 46 40">
                    <path fill="#E1DED8" d="M45.919 24.287c0 9.907-6.96 15.713-22.96 15.713S0 34.194 0 24.287C0 14.381 8.323 6.565 22.96 6.565c14.636 0 22.959 7.816 22.959 17.722Z"/>
                    <path fill="#E1DED8" d="M5.225 6.076c-.06-1.469 1.63-2.332 2.785-1.424l4.93 3.878c.361.284.476.774.204 1.144-.464.633-1.374 1.61-2.971 2.423-1.603.817-3 1.014-3.836 1.043-.481.018-.841-.374-.86-.855l-.253-6.21Zm35.512-.287c.06-1.469-1.63-2.332-2.785-1.424L33.02 8.243c-.36.284-.476.774-.204 1.144.465.633 1.374 1.61 2.972 2.423 1.603.817 2.999 1.013 3.836 1.043.48.018.84-.374.86-.855l.253-6.21Z"/>
                    <mask id="a" fill="#fff">
                      <path fill-rule="evenodd" d="M5.015 5.572c.024-1.377 1.575-2.17 2.706-1.383l5.417 3.77c2.852-.898 6.137-1.394 9.821-1.394 3.672 0 6.947.492 9.793 1.386l5.404-3.762c1.13-.787 2.681.006 2.705 1.383l.12 6.923a.84.84 0 0 1-.007.142c3.234 3.098 4.945 7.16 4.945 11.65 0 9.907-6.96 15.713-22.96 15.713S0 34.194 0 24.287c0-4.474 1.698-8.521 4.908-11.615a.998.998 0 0 1-.013-.177l.12-6.923Z" clip-rule="evenodd"/>
                    </mask>
                    <path fill="#E1DED8" d="m7.72 4.189.493-.707-.492.707ZM5.016 5.572l.861.015-.86-.015Zm8.123 2.388-.492.707.347.241.404-.127-.259-.821Zm19.614-.01-.258.822.403.127.346-.242-.491-.706Zm5.404-3.761-.492-.707.492.707Zm2.705 1.383-.86.015.86-.015Zm.12 6.923.861-.015-.86.015Zm-.007.142-.854-.107-.054.429.313.3.595-.622Zm-36.066.035.597.62.325-.313-.073-.445-.85.138Zm-.013-.177.86.015-.86-.015Zm3.318-9.013c-1.696-1.18-4.023.009-4.059 2.075l1.722.03a.861.861 0 0 1 1.353-.692l.984-1.413Zm5.417 3.771L8.213 3.482l-.984 1.413 5.417 3.772.984-1.414Zm9.33-1.549c-3.762 0-7.135.506-10.08 1.435l.517 1.642c2.758-.87 5.954-1.355 9.562-1.355V5.704ZM33.01 7.13c-2.94-.922-6.302-1.425-10.05-1.425v1.722c3.595 0 6.782.482 9.534 1.346l.516-1.643Zm4.654-3.647L32.26 7.244l.983 1.413 5.405-3.762-.984-1.413Zm4.058 2.075C41.686 3.49 39.36 2.3 37.664 3.482l.984 1.413A.861.861 0 0 1 40 5.587l1.722-.03Zm.12 6.923-.12-6.923-1.721.03.12 6.923 1.721-.03Zm-.014.263c.011-.086.016-.174.014-.263l-1.721.03a.15.15 0 0 1-.001.02l1.709.213Zm4.952 11.544c0-4.722-1.804-9.01-5.21-12.272l-1.191 1.243c3.062 2.934 4.679 6.77 4.679 11.03h1.722ZM22.96 40.861c8.078 0 14.03-1.461 17.982-4.304 4.002-2.879 5.838-7.09 5.838-12.27h-1.722c0 4.727-1.645 8.372-5.122 10.873-3.528 2.537-9.056 3.979-16.977 3.979v1.722ZM-.862 24.287c0 5.18 1.835 9.391 5.838 12.27 3.951 2.843 9.903 4.304 17.982 4.304v-1.722c-7.92 0-13.448-1.442-16.977-3.98C2.506 32.66.861 29.015.861 24.288H-.861ZM4.31 12.052C.93 15.311-.86 19.583-.86 24.287H.861c0-4.243 1.605-8.066 4.644-10.995l-1.195-1.24Zm-.276.428c-.002.111.006.222.024.33l1.7-.276a.136.136 0 0 1-.002-.024l-1.722-.03Zm.12-6.923-.12 6.923 1.722.03.12-6.923-1.722-.03Z" mask="url(#a)"/>
                    <ellipse cx="22.959" cy="24.574" fill="#E1DED8" rx="12.628" ry="8.968"/>
                    <circle cx="15.498" cy="23.211" r="1.435" fill="#1C1917"/>
                    <circle cx="30.565" cy="23.211" r="1.435" fill="#1C1917"/>
                    <ellipse cx="22.959" cy="25.579" fill="#1C1917" rx="1.435" ry=".933"/>
                    <path stroke="#A8A29E" stroke-width=".717" d="M0-.359h3.129" transform="matrix(.94 .34117 -.36763 .92997 9.184 26.511)"/>
                    <path stroke="#A8A29E" stroke-width=".717" d="M0-.359h3.129" transform="matrix(.94 -.34117 -.36763 -.92997 9.184 30.099)"/>
                    <path stroke="#A8A29E" stroke-width=".717" d="M0-.359h3.129" transform="matrix(-.94 .34117 .36763 .92997 36.591 26.511)"/>
                    <path stroke="#A8A29E" stroke-width=".717" d="M0-.359h3.129" transform="matrix(-.94 -.34117 .36763 -.92997 36.591 30.099)"/>
                  </svg>

                </div>
                <div class="absolute left-0 z-0 pt-2 origin-left scale-[0.7] group-hover:left-14 transition-all duration-200 opacity-0 group-hover:opacity-100">
                  <svg xmlns="http://www.w3.org/2000/svg" width="84" height="40" fill="none" viewBox="0 0 84 40">
                    <path fill="#78716C" d="M12.919 16c0-8.837 7.163-16 16-16h39c8.836 0 16 7.163 16 16v8c0 8.837-7.164 16-16 16h-39c-8.837 0-16-7.163-16-16v-8Z"/>
                    <path fill="#fff" d="M35.607 25.192a6.89 6.89 0 0 1-2.416-.416 5.775 5.775 0 0 1-1.92-1.216 5.71 5.71 0 0 1-1.28-1.84 5.88 5.88 0 0 1-.448-2.32c0-.843.149-1.616.448-2.32a5.71 5.71 0 0 1 1.28-1.84 5.744 5.744 0 0 1 1.936-1.2 6.574 6.574 0 0 1 2.416-.432c.97 0 1.845.17 2.624.512.789.33 1.45.821 1.984 1.472l-1.664 1.536a3.797 3.797 0 0 0-1.28-.976 3.52 3.52 0 0 0-1.536-.336c-.523 0-1.003.085-1.44.256-.438.17-.816.416-1.136.736-.32.32-.571.699-.752 1.136a3.967 3.967 0 0 0-.256 1.456c0 .533.085 1.019.256 1.456.181.437.432.816.752 1.136.32.32.698.565 1.136.736.437.17.917.256 1.44.256.554 0 1.066-.107 1.536-.32a3.91 3.91 0 0 0 1.28-1.008l1.664 1.536a5.186 5.186 0 0 1-1.984 1.488c-.779.341-1.659.512-2.64.512ZM47.358 25v-1.68l-.16-.368v-3.008c0-.533-.165-.95-.496-1.248-.32-.299-.816-.448-1.488-.448-.459 0-.912.075-1.36.224-.437.139-.81.33-1.12.576l-.896-1.744c.47-.33 1.035-.587 1.696-.768a7.591 7.591 0 0 1 2.016-.272c1.312 0 2.33.31 3.056.928.725.619 1.088 1.584 1.088 2.896V25h-2.336Zm-2.624.128c-.672 0-1.248-.112-1.728-.336-.48-.235-.848-.55-1.104-.944a2.388 2.388 0 0 1-.384-1.328c0-.512.123-.96.368-1.344.256-.384.656-.683 1.2-.896.544-.224 1.254-.336 2.128-.336h2.288V21.4h-2.016c-.586 0-.992.096-1.216.288a.929.929 0 0 0-.32.72c0 .32.123.576.368.768.256.181.603.272 1.04.272.416 0 .79-.096 1.12-.288.33-.203.57-.496.72-.88l.384 1.152a2.228 2.228 0 0 1-.992 1.264c-.48.288-1.099.432-1.856.432ZM52.577 25v-8.8c0-.97.288-1.744.864-2.32.576-.587 1.398-.88 2.464-.88.363 0 .71.037 1.04.112.341.075.63.192.864.352l-.656 1.808a1.7 1.7 0 0 0-.464-.224 1.815 1.815 0 0 0-.544-.08c-.363 0-.645.107-.848.32-.192.203-.288.512-.288.928v.8l.064 1.072V25h-2.496Zm-1.328-6.496v-1.92h5.968v1.92H51.25Zm11.694 6.624c-.981 0-1.845-.192-2.592-.576-.736-.384-1.306-.907-1.712-1.568-.405-.672-.608-1.435-.608-2.288 0-.864.198-1.627.592-2.288a4.236 4.236 0 0 1 1.648-1.568c.694-.384 1.478-.576 2.352-.576.843 0 1.6.181 2.272.544a3.93 3.93 0 0 1 1.616 1.536c.395.661.592 1.456.592 2.384 0 .096-.005.208-.016.336-.01.117-.021.23-.032.336h-6.992v-1.456h5.68l-.96.432c0-.448-.09-.837-.272-1.168a1.93 1.93 0 0 0-.752-.768 2.135 2.135 0 0 0-1.12-.288 2.22 2.22 0 0 0-1.136.288 1.91 1.91 0 0 0-.752.784c-.181.33-.272.725-.272 1.184v.384c0 .47.102.885.304 1.248.214.352.507.624.88.816.384.181.832.272 1.344.272.459 0 .859-.07 1.2-.208a2.92 2.92 0 0 0 .96-.624l1.328 1.44a3.93 3.93 0 0 1-1.488 1.04c-.597.235-1.285.352-2.064.352Z"/>
                    <g clip-path="url(#a)">
                      <path fill="#78716C" d="M-1.75 19.968 15.5 12v15.935l-17.25-7.967Z"/>
                    </g>
                    <defs>
                      <clipPath id="a">
                        <path fill="#fff" d="M15 12v16H0V12z"/>
                      </clipPath>
                    </defs>
                  </svg>
                </div>
              </div>
            </RouterLink>
          </div>
        </div>

        <!-- Web Menu -->
        <div class="flex gap-10 justify-center items-center">
          <div class="hidden lg:block">
            <div class="whitespace-nowrap sm:flex sm:flex-row sm:justify-between">
              <ul class="flex flex-col gap-2 items-center text-sm font-semibold sm:flex-row">
                <!-- Menu -->
                <li v-for="item in menuItems" :key="item.to">
                  <RouterLink :to="item.to" 
                    class="flex items-center px-4 py-2.5 whitespace-nowrap transition-colors duration-200 sm:px-5"
                    :class="isActive(item.to) ? 'text-stone-900 dark:text-white' : 'text-stone-400 hover:text-stone-900 dark:hover:text-white'">
                    {{ $t(item.text) }}
                  </RouterLink>
                </li>
                <!-- Heart Icon for Wishlist -->
                <li class="">
                  <RouterLink to="/wishlist">
                    <!-- Heart Icon -->
                    <div class="p-2">
                      <SolarHeartLinear class="text-xl" />
                    </div>
                  </RouterLink>
                </li>
                <!-- Cart Icon -->
                <li class="flex relative items-center">
                  <button @click="isCartOpen = !isCartOpen" class="relative">
                    <div class="p-2">
                      <SolarCart3Linear class="text-xl" />
                      <!-- Badge showing cart item count -->
                      <span
                        v-if="cartCount > 0"
                        class="flex absolute -top-1 -right-1 justify-center items-center w-5 h-5 text-xs font-bold text-white bg-red-500 rounded-full"
                      >
                        {{ cartCount }}
                      </span>
                    </div>
                  </button>
                </li>
                <!-- User Icon -->
                <button @click="isSignupDrawerOpen = !isSignupDrawerOpen" class="">
                  <div class="p-2">
                    <SolarUserLinear class="text-xl" />
                  </div>
                </button>
                <!-- Language -->
                <!-- <LanguageSwitcher /> -->
                <!-- Dark Toggle -->
                <DarkModeToggle />
              </ul>
            </div>
          </div>
        </div>
        <div class="flex gap-2 items-center">
          <!-- Pass the toggleMenu method and isOpen state -->
          <!-- Heart Icon for Wishlist -->
          <RouterLink to="/wishlist" class="lg:hidden">
            <!-- Heart Icon -->
            <div class="p-2">
              <SolarHeartLinear class="text-xl" />
            </div>
          </RouterLink>
          <!-- Cart Icon -->
          <button @click="isCartOpen = !isCartOpen" class="block relative lg:hidden">
            <div class="p-2">
              <SolarCart3Linear class="text-xl" />
              <!-- Badge showing cart item count -->
              <span
                v-if="cartCount > 0"
                class="flex absolute -top-1 -right-1 justify-center items-center w-5 h-5 text-xs font-bold text-white bg-red-500 rounded-full"
              >
                {{ cartCount }}
              </span>
            </div>
          </button>
          <!-- User Icon -->
          <button @click="isSignupDrawerOpen = !isSignupDrawerOpen" class="lg:hidden">
            <div class="p-2">
              <SolarUserLinear class="text-xl" />
            </div>
          </button>
          <Hamburger :toggleMenu="toggleMenu" :isOpen="showMenu" />
        </div>
      </div>
      <!-- Mobile Menu -->
      <div class="lg:hidden">
        <div v-if="showMenu" class="fixed inset-0 backdrop-blur-lg bg-black/20 -z-10 xl:hidden" @click="toggleMenu"></div>
        <div v-if="showMenu" class="flex z-20 flex-col justify-between p-2.5 whitespace-nowrap md:p-5">
          <ul class="flex flex-col gap-2 text-sm font-semibold">
            <!-- Menu -->
            <li v-for="item in menuItems" :key="item.to">
              <RouterLink :to="item.to" 
                class="flex items-center px-2 py-2.5 whitespace-nowrap transition-colors duration-200"
                :class="isActive(item.to) ? 'text-white dark:text-stone-900' : 'text-stone-500 hover:text-white'">
                {{ $t(item.text) }}
              </RouterLink>
            </li>
            <li class="flex gap-2">
              <!-- Language -->
              <!-- <LanguageSwitcher class="border-2 border-stone-50" /> -->
              <!-- Dark Toggle -->
              <DarkModeToggle class="border-2 border-stone-50" />
            </li>
          </ul>
        </div>
      </div>
    </div>

  </div>
  <!-- 購物車 Drawer -->
  <Cart :isOpen="isCartOpen" @close-cart="isCartOpen = false" />
  <!-- 登入 Drawer -->
  <SignupDrawer :isOpen="isSignupDrawerOpen" @close="isSignupDrawerOpen = false" />

</template>

<script>
import { computed, ref, onMounted, onBeforeUnmount } from "vue";
import { useRoute, useRouter } from 'vue-router';
import { useStore } from 'vuex';
import MingcuteEarth3Fill from '~icons/mingcute/earth-3-fill';

export default {
  components: {
    MingcuteEarth3Fill,
  },
  data() {
    return {
      icon: MingcuteEarth3Fill,
      isCartOpen: false, // Add this line to manage the cart drawer state
      isSignupDrawerOpen: false,
    };
  },
  setup() {
    const route = useRoute();
    const router = useRouter();
    const store = useStore();
    const showMenu = ref(false);
    const isVisible = ref(true);
    const lastScrollY = ref(window.scrollY);

    const cartItems = computed(() => store.getters.cartItems);
    const cartCount = computed(() => cartItems.value.reduce((acc, item) => acc + item.quantity, 0));

    const toggleMenu = () => showMenu.value = !showMenu.value;

    // Update main menu items based on your pages structure
    const menuItems = [
      { to: '/', text: '找咖啡廳' }, // Home page
      { to: '/recipe', text: '咖啡食譜' }, // Blog listing page
      { to: '/shop', text: '所有商品' }, // Shop
      { to: '/about', text: '關於我' }, // Contact page
    ];

    const isActive = (path) => route.path === path;

    const handleScroll = () => {
      isVisible.value = window.scrollY <= 10;
      lastScrollY.value = window.scrollY;
    };

    onMounted(() => window.addEventListener('scroll', handleScroll));
    onBeforeUnmount(() => window.removeEventListener('scroll', handleScroll));

    return { cartCount, menuItems, toggleMenu, isActive, showMenu, isVisible };
  },
};
</script>

<style scoped>
/* Add styles if needed */
</style>
