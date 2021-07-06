<template>
  <dashboard-provider>
    <div
      class="
        base
        bg-mac bg-center bg-cover
        h-screen
        overflow-hidden
        w-full
        lg:p-4
      "
    >
      <div class="content h-screen overflow-hidden relative lg:rounded-2xl">
        <div class="flex items-start">
          <Overlay />
          <side-navigation mobile-position="right" />
          <div class="flex flex-col h-screen pl-0 w-full lg:space-y-4 lg:w-99">
            <top-navigation />
            <main
              class="
                main
                h-screen
                overflow-auto
                pb-36
                pt-4
                px-2
                text-black
                md:pb-8 md:px-4
                lg:mt-4 lg:px-6
              "
            >
              <slot />
            </main>
          </div>
        </div>
      </div>
    </div>
  </dashboard-provider>
</template>

<script>
import Overlay from './provider/Overlay.vue'
import TopNavigation from './topnavigation/Index.vue'
import SideNavigation from './sidenavigation/Index.vue'
import DashboardProvider from './provider/Provider.vue'

export default {
  name: 'DashboardLayout',
  components: { DashboardProvider, Overlay, SideNavigation, TopNavigation },
}
</script>

<style scoped>
.base:before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  background: linear-gradient(
    180deg,
    rgba(255, 255, 255, 0.72) 0%,
    rgba(255, 255, 255, 0.45) 100%
  );
  -webkit-backdrop-filter: saturate(3);
  backdrop-filter: saturate(3);
}

.content {
  background-color: rgb(255 255 255 / 31%);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
}

.main {
  background-color: rgb(255 255 255 / 31%);
}

.main::-webkit-scrollbar {
  width: 6px;
  border-radius: 10px;
}

.main::-webkit-scrollbar-thumb {
  background: rgb(1 2 3 / 40%);
  border-radius: 10px;
}
</style>
