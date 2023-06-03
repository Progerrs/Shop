<template>
  <div class="flex flex-col h-screen">


    <div class="p-2 my-2 rounded-full hover:bg-blue-50 w-min dark:hover:bg-white/20" :class="defaultTransition">
      <nuxt-link to="/">
        <div class="w-8 h-8">
          <LogoTwitter />
        </div>
      </nuxt-link>
    </div>

    <div class="mt-2 space-y-3">
      <SidebarLeftTab active>
        <template v-slot:icon>
          <icon-home />
        </template>
        <template v-slot:name>
          Главная
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab>
        <template v-slot:icon>
          <div class="relative">
            <icon-notification />
            <div class="absolute flex items-center justify-center w-4 h-4 bg-blue-400 rounded-full top-0 right-0 -mt-2 -mr-2">
              <span class="text-white text-xs font-semibold flex items-center justify-center">
                1
              </span>
            </div>
          </div>

        </template>
        <template v-slot:name>
          Уведомления
        </template>
      </SidebarLeftTab>


      <SidebarLeftTab>
        <template v-slot:icon>
          <icon-chat />
        </template>
        <template v-slot:name>
          Сообщество
        </template>
      </SidebarLeftTab>

      <SidebarLeftTab>
        <template v-slot:icon>
          <icon-bookmark />
        </template>
        <template v-slot:name>
          Закладки
        </template>
      </SidebarLeftTab>


      <SidebarLeftTab>
        <template v-slot:icon>
          <icon-user />
        </template>
        <template v-slot:name>
          Профиль
        </template>
      </SidebarLeftTab>

      <div class="hidden xl:block">
        <UIButton  liquid size="lg" @click="handleToggleDarkMode">
                    <span class="font-bold">
                        Сменить тему
                    </span>
        </UIButton >
      </div>
      <div class="block xl:hidden">
        <UIButton @click="handleToggleDarkMode">
          <div class="w-6 h-6 font-bold">
            <icon-dark />
          </div>
        </UIButton>
      </div>
    </div>
    <div class="flex flex-row items-center justify-center px-2 py-2 mx-auto mt-auto mb-5 rounded-full cursor-pointer w-14 xl:w-full hover:bg-gray-100 dark:hover:bg-dim-800"
         :class="defaultTransition" @click="emits('onLogout')">
      <div class="flex flex-row">
        <img src="https://www.hist.msu.ru/Departments/Inf/Stud/IMG/Translat/Planet00.jpg" class="w-10 h-10 rounded-full">
        <div class="flex-col hidden ml-2 xl:block">
          <h1 class="text-sm font-bold text-gray-800 dark:text-white">
<!--            {{ user.name }}-->
            Test
          </h1>
          <p class="text-sm text-gray-400">
            Serega
<!--            {{ user.handle }}-->
          </p>
        </div>
      </div>
      <!-- ICON -->
      <div class="hidden ml-auto xl:block">
        <div class="w-6 h-6">
          <icon-down />
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>

const { defaultTransition } = useTailwindConfig()
const emits = defineEmits(['onTweet', 'onLogout', 'toggleDarkMode'])
function handleToggleDarkMode() {
  emits('toggleDarkMode')
}


const props = defineProps({
  user: {
    type: Object,
    required: true
  }
})


</script>