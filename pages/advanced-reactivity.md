---
---

<div class="grid grid-cols-2 gap-x-4"><div>

# watchEffect vs watch

```ts {monaco}
import { ref, watch, watchEffect } from 'vue'

const count = ref(0)

// watchEffect - runs immediately
watchEffect(() => {
  console.log('Count is:', count.value)
})

// watch - explicit dependencies
watch(count, (newVal, oldVal) => {
  console.log(`${oldVal} -> ${newVal}`)
})
```

<div v-click>

###### Key Differences
- **watchEffect**: Auto-tracks dependencies
- **watch**: Explicit source tracking
- **watchEffect**: Always runs immediately

</div>

</div><div>

<div v-click="2">

# When to Use Each

```ts {monaco}
// Use watchEffect for side effects
watchEffect(() => {
  document.title = `Count: ${count.value}`
})

// Use watch for specific reactions
watch(
  () => user.name,
  (newName) => {
    saveUserName(newName)
  },
  { immediate: true }
)
```

</div>

</div></div>
