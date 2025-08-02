<template>
  <footer
    v-if="
      $slidev.nav.currentLayout !== 'cover' &&
      $slidev.nav.currentPage !== 2 &&
      $slidev.nav.currentPage !== $slidev.nav.total + 1
    "
    class="absolute bottom-0 right-0 p-2"
  >
    {{ $slidev.nav.currentPage }}
  </footer>
</template>
