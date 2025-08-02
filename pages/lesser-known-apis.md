---
---

<div class="grid grid-cols-2 gap-x-4"><div>

# Teleport

```vue {monaco}
<template>
  <div>
    <button @click="showModal = true">
      Open Modal
    </button>
    
    <Teleport to="body">
      <div v-if="showModal" class="modal">
        <div class="modal-content">
          <h3>Modal Title</h3>
          <button @click="showModal = false">
            Close
          </button>
        </div>
      </div>
    </Teleport>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const showModal = ref(false)
</script>
```

</div><div>

<div v-click>

# Provide/Inject

```ts {monaco}
// Parent Component
import { provide } from 'vue'

provide('theme', 'dark')
provide('user', { name: 'John', role: 'admin' })

// Child Component (any level deep)
import { inject } from 'vue'

const theme = inject('theme', 'light') // default value
const user = inject('user')
```

###### Use Cases
- **Theme systems**
- **User authentication**
- **Global configurations**

</div>

</div></div>
