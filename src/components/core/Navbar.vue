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
                  <img class="block dark:hidden" src="/src/assets/Icon.svg" alt="">
                  <!-- Dark -->
                  <img class="hidden dark:block"  src="/src/assets/Icon-d.svg" alt="">
                </div>
                <div class="absolute left-0 z-0 pt-2 origin-left scale-[0.7] group-hover:left-14 transition-all duration-200 opacity-0 group-hover:opacity-100 group-hover:ease-in-out">
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
import { computed, ref, onMounted, onBeforeUnmount, watch } from "vue";
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

    watch(showMenu, (newVal) => {
      document.body.style.overflow = newVal ? "hidden" : "";
    });

    // 監聽路由變化，關閉 Menu
    watch(route, () => (showMenu.value = false));

    // 組件卸載時確保恢復滾動
    onBeforeUnmount(() => (document.body.style.overflow = ""));

    // 切換菜單
    const toggleMenu = () => (showMenu.value = !showMenu.value);

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
