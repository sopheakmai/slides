---
---

<div class="grid grid-cols-2 gap-x-4"><div>

# Dynamic Components

```vue {monaco}
<template>
  <div>
    <button 
      v-for="tab in tabs" 
      :key="tab"
      @click="currentTab = tab"
    >
      {{ tab }}
    </button>
    
    <component 
      :is="currentComponent" 
      v-bind="componentProps"
    />
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import Home from './Home.vue'
import About from './About.vue'

const tabs = ['Home', 'About']
const currentTab = ref('Home')

const components = { Home, About }

const currentComponent = computed(() => 
  components[currentTab.value]
)
</script>
```

</div><div>

<div v-click>

###### Benefits
- **Tab interfaces**
- **Conditional rendering**
- **Dynamic layouts**
- **Plugin systems**

</div>

<div v-click="2" class="mt-8">

###### Keep Alive

```vue {monaco}
<template>
  <KeepAlive>
    <component :is="currentComponent" />
  </KeepAlive>
</template>
```

**Preserves component state** when switching between components

</div>

</div></div>
