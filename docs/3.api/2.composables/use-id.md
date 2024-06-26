---
title: "useId"
description: Generate an SSR-friendly unique identifier that can be passed to accessibility attributes.
links:
  - label: Source
    icon: i-simple-icons-github
    to: https://github.com/nuxt/nuxt/blob/main/packages/nuxt/src/app/composables/id.ts
    size: xs
---

::important
This composable is available since [Nuxt v3.10](/blog/v3-10#ssr-safe-accessible-unique-id-creation).
::

`useId` generates an SSR-friendly unique identifier that can be passed to accessibility attributes.

Call `useId` at the top level of your component to generate a unique string identifier:

```vue [components/EmailField.vue]
<script setup lang="ts">
const id = useId()
</script>

<template>
  <div>
    <label :for="id">Email</label>
    <input :id="id" name="email" type="email" />
  </div>
</template>
```

::note
`useId` must be used in a component with a single root element, as it uses this root element's attributes to pass the id from server to client.
::

## Parameters

`useId` does not take any parameters.

## Returns

`useId` returns a unique string associated with this particular `useId` call in this particular component.
