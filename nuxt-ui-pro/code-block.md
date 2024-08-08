---
title: CodeBlock
description: A code-block with automatic syntax highlighting, filename and copy button.
---

## Usage

Code blocks are rendered by the `ProseCode` component of [Nuxt Content](https://content.nuxt.com/usage/markdown#code-highlighting) and syntax highlighting is done underneath by [Shikiji](https://github.com/antfu/shikiji).

By default for syntax highlighting, `material-theme-lighter` and `material-theme-palenight` VSCode themes are used for light & dark mode respectively. You can change this in your `nuxt.config.ts` through the [`content.highlight`](https://content.nuxt.com/get-started/configuration#highlight) key.

Nuxt UI Pro overrides the [`ProseCode`](https://content.nuxt.com/components/prose#prosecode) component to add some extra features like a copy button, a filename and automatic icons.

::component-example
---
prose: true
extraClass: 'flex-col [&>div>pre]:!my-0'
---

```ts
export default defineNuxtConfig({
  extends: ['@nuxt/ui-pro'],
  modules: ['@nuxt/ui']
})
```

#code
````md
```ts
export default defineNuxtConfig({
  extends: ['@nuxt/ui-pro'],
  modules: ['@nuxt/ui']
})
```
````
::

### Name

When using a `CodeBlock`, you can specify a filename that will be displayed on top of the code block.

::component-example
---
prose: true
extraClass: 'flex-col [&>div]:!my-0'
---

```ts [nuxt.config.ts]
export default defineNuxtConfig({
  extends: ['@nuxt/ui-pro'],
  modules: ['@nuxt/ui']
})
```

#code
````md
```ts [nuxt.config.ts]
export default defineNuxtConfig({
  extends: ['@nuxt/ui-pro'],
  modules: ['@nuxt/ui']
})
```
````
::

### Icon

When specifying a filename, an icon will be automatically displayed based on the extension or the name.

Some icons are already defined by default, but you can add more in your `app.config.ts` through the `ui.content.prose.code.icon` key:

```ts
export default defineAppConfig({
  ui: {
    content: {
      prose: {
        code: {
          icon: {
            terminal: 'i-ph-terminal-window-duotone'
          }
        }
      }
    }
  }
})
```

Here is the default mapping:

```ts
{
  'package.json': 'vscode-icons:file-type-node',
  'tsconfig.json': 'vscode-icons:file-type-tsconfig',
  '.npmrc': 'vscode-icons:file-type-npm',
  '.editorconfig': 'vscode-icons:file-type-editorconfig',
  '.eslintrc': 'vscode-icons:file-type-eslint',
  '.eslintrc.cjs': 'vscode-icons:file-type-eslint',
  '.eslintignore': 'vscode-icons:file-type-eslint',
  'eslint.config.js': 'vscode-icons:file-type-eslint',
  'eslint.config.mjs': 'vscode-icons:file-type-eslint',
  'eslint.config.cjs': 'vscode-icons:file-type-eslint',
  '.gitignore': 'vscode-icons:file-type-git',
  'yarn.lock': 'vscode-icons:file-type-yarn',
  '.env': 'vscode-icons:file-type-dotenv',
  '.env.example': 'vscode-icons:file-type-dotenv',
  '.vscode/settings.json': 'vscode-icons:file-type-vscode',
  'nuxt': 'vscode-icons:file-type-nuxt',
  '.nuxtrc': 'vscode-icons:file-type-nuxt',
  '.nuxtignore': 'vscode-icons:file-type-nuxt',
  'nuxt.config.js': 'vscode-icons:file-type-nuxt',
  'nuxt.config.ts': 'vscode-icons:file-type-nuxt',
  'nuxt.schema.ts': 'vscode-icons:file-type-nuxt',
  'tailwind.config.js': 'vscode-icons:file-type-tailwind',
  'tailwind.config.ts': 'vscode-icons:file-type-tailwind',
  vue: 'vscode-icons:file-type-vue',
  ts: 'vscode-icons:file-type-typescript',
  tsx: 'vscode-icons:file-type-typescript',
  mjs: 'vscode-icons:file-type-js',
  cjs: 'vscode-icons:file-type-js',
  js: 'vscode-icons:file-type-js',
  jsx: 'vscode-icons:file-type-js',
  md: 'vscode-icons:file-type-markdown',
  py: 'vscode-icons:file-type-python',
  ico: 'vscode-icons:file-type-favicon',
  npm: 'vscode-icons:file-type-npm',
  pnpm: 'vscode-icons:file-type-pnpm',
  npx: 'vscode-icons:file-type-npm',
  yarn: 'vscode-icons:file-type-yarn',
  bun: 'vscode-icons:file-type-bun',
  yml: 'vscode-icons:file-type-yaml',
  terminal: 'i-heroicons-command-line'
}
```

### Copy

Every code block has a copy button that will copy the code to your clipboard. You can change the icon in your `app.config.ts` through the `ui.content.prose.code.button.icon` key:

```ts
export default defineAppConfig({
  ui: {
    content: {
      prose: {
        code: {
          button: {
            icon: {
              copy: 'i-ph-copy-duotone',
              copied: 'i-ph-check-square-duotone'
            }
          }
        }
      }
    }
  }
})
```
