
# clickable theme extends vite-pages-theme-doc

a custom theme of [vite-plugin-react-pages](https://vitejs.github.io/vite-plugin-react-pages) (vite-pages) ,simply extends `topNavs` type in [official-theme](https://vitejs.github.io/vite-plugin-react-pages/official-theme).  



## features 
customize menu item, with two features
1. click events
2. set JSX Element instead of string.
3. compitable with official theme `vite-pages-theme-doc@5.0.0`


My component library have 30+ themes, so I can make the top Nav menu act as a theme selector.
![alt text](image.png)


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
            setTheme(key) //   😕
          },
          element: <jsx-element/>, // 😽
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


## type definition

```ts
type MenuConfig =
... // original type
  | {
      readonly key: string
      readonly element: React.JSX.Element | string
      onclick?: TitleClick
    }
```


[source code](https://github.com/shawspring/vite-plugin-react-pages/blob/main/packages/theme-doc/src/Layout/renderMenu.tsx)



