# A fork of vite-plugin-react-pages
just for **customize official** theme, focus on workspace `packages/theme-doc` 
[Checkout the official-theme](https://vitejs.github.io/vite-plugin-react-pages/official-theme).
[vite-plugin-react-pages](https://vitejs.github.io/vite-plugin-react-pages) (vite-pages) is a React app framework powered by [vite](https://github.com/vitejs/vite). It is very suitable for:


## my custom theme
### feature
customize menu item click events.
My component library have 30+ themes, so I need the menu act as a theme selector.

## usage
> be careful, '@shawspring/vite-pages-theme-doc' replace 'vite-plugin-react-pages'
```bash
npm install -D @shawspring/vite-pages-theme-doc
```

```ts
import { createTheme } from '@shawspring/vite-pages-theme-doc'
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


dev preview

workspace `packages/create-project/template-lib` use for  preview
> import { createTheme, defaultSideNavs } from 'vite-pages-theme-doc/src' not work, why?

