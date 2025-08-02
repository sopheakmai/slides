---
---

<div class="grid grid-cols-2 gap-x-4"><div>

# Scoped Slots

```vue {monaco}
<!-- Parent Component -->
<template>
  <UserList>
    <template #item="{ user, index }">
      <div class="user-card">
        <h3>{{ user.name }}</h3>
        <p>Position: {{ index + 1 }}</p>
      </div>
    </template>
  </UserList>
</template>
```

</div><div>

```vue {monaco}
<!-- UserList.vue -->
<template>
  <div>
    <div 
      v-for="(user, index) in users" 
      :key="user.id"
    >
      <slot 
        name="item" 
        :user="user" 
        :index="index" 
      />
    </div>
  </div>
</template>

<script setup>
const users = ref([
  { id: 1, name: 'John' },
  { id: 2, name: 'Jane' }
])
</script>
```

</div></div>

<div v-click class="mt-6 text-center">

###### **Key Benefit**: Parent controls rendering, child provides data

</div>

