---
---

<div class="grid grid-cols-2 gap-x-4"><div>

# toRefs & toRef

```ts {monaco}
import { reactive, toRefs, toRef } from 'vue'

const state = reactive({
  count: 0,
  name: 'John'
})

// Convert all properties to refs
const { count, name } = toRefs(state)

// Convert single property to ref
const count2 = toRef(state, 'count')

// Now destructuring works!
count.value++
```

<div v-click>

###### Problem Solved
- **Destructuring reactive objects**
- **Maintaining reactivity**

</div>

</div><div>

<div v-click="2">

# shallowRef & shallowReactive

```ts {monaco}
import { shallowRef, shallowReactive } from 'vue'

// Only .value is reactive
const shallowState = shallowRef({
  nested: { count: 0 }
})

// Only root level is reactive
const shallow = shallowReactive({
  count: 0, // ✅ reactive
  nested: { count: 0 } // ❌ NOT reactive
})
```

</div>

<div v-click="3" class="mt-4">

###### Use Cases
- **Performance optimization**
- **Large objects**
- **External libraries**

</div>

</div></div>
