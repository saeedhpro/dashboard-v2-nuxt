<template>
  <router-link :to="to">
    <span
      class="
        flex
        items-center
        justify-start
        my-1
        p-3
        text-gray-800
        w-full
        lg:hover:bg-gray-100
      "
      :class="
        $route.path === to &&
        'border-gray-700 border-l-4 lg:border-l-0 lg:border-r-4 lg:border-red-300'
      "
    >
      <span>
        <slot />
      </span>
      <span class="mx-4 text-sm">
        {{ title }}
      </span>
    </span>
  </router-link>
</template>

<script>
export default {
  name: 'SidenavItem',
  props: {
    to: {
      type: String,
      default: '',
    },
    title: {
      type: String,
      default: '',
    },
  },
}
</script>
