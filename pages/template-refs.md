---
---

<div class="grid grid-cols-2 gap-x-4"><div>

# Template Refs

```vue {monaco}
<template>
  <input ref="inputRef" />
  <button @click="focusInput">
    Focus Input
  </button>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const inputRef = ref()

const focusInput = () => {
  inputRef.value.focus()
}
</script>
```

</div><div>

<div v-click class="mt-12">

###### Key Points
- **Direct DOM access**
- Available after mount
- TypeScript: `ref<HTMLInputElement>()`

</div>

<div v-click="2" class="mt-8">

###### Common Use Cases
- **Focus management**
- **Scroll to element**
- **Measuring dimensions**
- **Third-party library integration**

</div>

</div></div>
