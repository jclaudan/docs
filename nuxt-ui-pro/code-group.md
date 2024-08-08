---
title: CodeGroup
description: Group code blocks together in tabs.
links:
  - label: GitHub
    icon: i-simple-icons-github
    to: https://github.com/nuxt/ui-pro/blob/dev/modules/pro/runtime/components/global/CodeGroup.vue
---

## Usage

Wrap your code blocks around a `CodeGroup` component:

::component-example
---
prose: true
---

::code-group{class="w-full !my-0"}

```bash [pnpm]
pnpm add @nuxt/ui
```

```bash [yarn]
yarn add @nuxt/ui
```

```bash [npm]
npm install @nuxt/ui
```

::

#code
````mdc
::code-group

```bash [pnpm]
pnpm add @nuxt/ui
```

```bash [yarn]
yarn add @nuxt/ui
```

```bash [npm]
npm install @nuxt/ui
```
::
````
::

Like the [`CodeBlock`](/pro/prose/code-block) component, filenames, icons and copy buttons are automatically supported.

::code-group

```ts [nuxt.config.ts]
export default defineNuxtConfig({
  ui: {
    icons: ['heroicons', 'simple-icons']
  }
})
```

```ts [app.config.ts]
export default defineAppConfig({
  ui: {
    primary: 'green'
  }
})
```

```ts [tailwind.config.ts]
export default <Partial<Config>> {
  theme: {
    extend: {
      colors: {
        green: {
          50: '#EFFDF5',
          100: '#D9FBE8',
          200: '#B3F5D1',
          300: '#75EDAE',
          400: '#00DC82',
          500: '#00C16A',
          600: '#00A155',
          700: '#007F45',
          800: '#016538',
          900: '#0A5331',
          950: '#052e16'
        }
      }
    }
  }
}
```
::

## Config

```yml
{
  wrapper: 'relative [&>div:last-child]:!my-0 [&>div:last-child]:!static my-5',
  header: 'flex items-center gap-1 border border-gray-200 dark:border-gray-700 border-b-0 rounded-t-md overflow-hidden p-2',
  tab: {
    base: 'px-2 py-1.5 focus:outline-none text-gray-700 dark:text-gray-200 text-sm rounded-md flex items-center gap-1.5',
    active: 'bg-gray-100 dark:bg-gray-800',
    inactive: 'hover:bg-gray-50 dark:hover:bg-gray-800/50',
    icon: {
      base: ''
    }
  }
}
```
