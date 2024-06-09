
# A fork of vite-plugin-react-pages
just for customize official theme, focus on workspace `packages/theme-doc` 

### my custom theme
feature: customize menu item click events.
My component library have 30+ themes, so I need the menu act as a theme selector.
```ts
 createTheme({
  topNavs: [
    {
      subMenu: 'themes',
      icon: '🎨',
      children: [
        {
          key: 'light',
          onclick: ({ key, domEvent }) => {
            setTheme(key) // fake code
          },
          element: 'ligth theme',
        },
        {
          key: 'dark',
          ...
        }
        ...
      ],
    },
  ],
  ...
 })
```


simply extend the MenuConfig, make menu item clickable, not just navigate to path or external link
```
//packages/theme-doc/src/Layout/renderMenu.tsx
type MenuConfig =
...
  | {
      readonly key: string
      readonly element: React.JSX.Element | string
      onclick?: TitleClick
    }
```


### preview

workspace `packages/create-project/template-lib` use for  preview
> import { createTheme, defaultSideNavs } from 'vite-pages-theme-doc/src' not work, why?


# 📘 vite-plugin-react-pages

<p>
  <a href="https://www.npmjs.com/package/vite-plugin-react-pages" target="_blank" rel="noopener"><img src="https://img.shields.io/npm/v/vite-plugin-react-pages.svg" alt="npm package" /></a>
</p>

[vite-plugin-react-pages](https://vitejs.github.io/vite-plugin-react-pages) (vite-pages) is a React app framework powered by [vite](https://github.com/vitejs/vite). It is very suitable for:

