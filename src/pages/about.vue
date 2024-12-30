<template>
  <div class="h-screen bg-B4 text-stone-900 dark:text-white">
    <Layout>
      <template #content>
        <div class="flex flex-col gap-8 items-center lg:flex-row sm:gap-12">
          <!-- Banner -->
          <div class="w-full lg:w-1/2">
            <ChatBubble class="mb-4 w-52" />
            <!-- 圖片 -->
            <div class="bg-cover bg-center border-2 border-stone-900 dark:border-white overflow-hidden mb-4 aspect-[3/2] bg-[url('https://i.pinimg.com/control/564x/b5/b4/f9/b5b4f9cad18a8a787c3dd9bd39fc2f5e.jpg')]">
            </div>
          </div>
          <!-- Title -->
          <div class="w-full lg:w-1/2">
            <h1 class="mb-6 text-xl font-bold sm:mb-8 sm:text-2xl">
              Hey，很高興認識你！
            </h1>
            <p class="text-sm font-medium sm:text-base text-stone-800 dark:text-stone-300">
              我是一名 UI/UX 設計師，這是我對於咖啡廳資料庫及登入等功能的練習專案，希望你會喜歡！
            </p>
          </div>
        </div>
      </template>
    </Layout>
  </div>
</template>

<script>
export default {
};
</script>