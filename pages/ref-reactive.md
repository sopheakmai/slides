---
---

<div class="grid grid-cols-2 gap-x-4"><div>

# Ref

```ts {monaco}
import { ref } from 'vue'

let count = ref(0)
count.value = 1

// TypeScript catches this
count = 1 // ❌ Error
```

<div v-click>

###### When to use
- **Primitives** (string, number, boolean)
- **Single values**
- **TypeScript projects**

</div>

</div><div>

# Reactive

```ts {monaco}
import { reactive } from 'vue'

const state = reactive({
  count: 0,
  user: { name: 'John' }
})

state.count = 1
state.user.name = 'Jane'
```

<div v-click>

###### When to use
- **Objects and arrays**
- **Multiple related values**
- **Natural object syntax**

</div>

</div></div>

