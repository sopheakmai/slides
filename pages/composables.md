---
---

<div class="grid grid-cols-2 gap-x-4"><div>

# Creating Composables

```ts {monaco}
// useCounter.ts
import { ref, computed } from 'vue'

export function useCounter(initial = 0) {
  const count = ref(initial)
  
  const doubleCount = computed(() => 
    count.value * 2
  )
  
  const increment = () => count.value++
  const decrement = () => count.value--
  const reset = () => count.value = initial
  
  return {
    count: readonly(count),
    doubleCount,
    increment,
    decrement,
    reset
  }
}
```

</div><div>

<div v-click>

###### Usage in Components

```vue {monaco}
<template>
  <div>
    <p>Count: {{ count }}</p>
    <p>Double: {{ doubleCount }}</p>
    
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
    <button @click="reset">Reset</button>
  </div>
</template>

<script setup>
import { useCounter } from './composables/useCounter'

const {
  count,
  doubleCount,
  increment,
  decrement,
  reset
} = useCounter(10)
</script>
```

</div>

</div></div>
