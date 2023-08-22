
## Vue Version (install particular version)

```
yarn global add @vue/cli@5.0.4

```
## manual Install

- ### step 1

```
? Please pick a preset: Manually select features
? Check the features needed for your project: (Press <space> to select, <a> to toggle all, <i> to invert selection, and <enter> to proceed)
 ◉ Babel
 ◯ TypeScript
 ◉ Progressive Web App (PWA) Support
 ◉ Router
 ◉ Vuex
 ◉ CSS Pre-processors
 ◉ Linter / Formatter
 ◯ Unit Testing
❯◯ E2E Testing


```

- ### Step 2

```
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, PWA, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with (Use arrow keys)
❯ 3.x 
  2.x 

```

- ###step 3 
```
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, PWA, Router, Vuex, CSS Pre-processors, Linter
? Choose a version of Vue.js that you want to start the project with 3.x
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS (with dart-sass)
? Pick a linter / formatter config: Basic
? Pick additional lint features: Lint on save
? Where do you prefer placing config for Babel, ESLint, etc.? In package.json
? Save this as a preset for future projects? Yes
? Save preset as:
```


### Tailwind Css Install Process

- Reference Link (https://medium.com/featurepreneur/set-up-tailwind-css-for-your-vue-js-app-5a8801fd0a55)
  
  ```
    Step -1

      npm install -D tailwindcss@latest postcss@latest autoprefixer@latest
    
    Step -2

      npx tailwindcss init -p

    Step -3

      In the tailwind.config.js file,
      - replace purge: []
      - with purge: ['./index.html', './src/**/*.{vue,js,ts,jsx,tsx}']
    
    Step -4

      Under the src folder create index.css and add the following.

        /* ./src/index.css */
        @tailwind base;
        @tailwind components;
        @tailwind utilities;
    
    Step -5

          In the main.js file (in src folder), import index.css

          import "./index.css"

  ```

  ### Install tailwind plugins

  ```
   npm install -D @tailwindcss/forms
  
  ```

  ### Tailwind Conf page

  ```
  module.exports = {
    purge: ['./index.html', './src/**/*.{vue,js,ts,jsx,tsx}'],
    darkMode: false, // or 'media' or 'class'
    theme: {
        // colors: {
        //     'blue': '#1fb6ff',
        //     'purple': '#7e5bef',
        //     'pink': '#ff49db',
        //     'orange': '#ff7849',
        //     'green': '#13ce66',
        //     'yellow': '#ffc82c',
        //     'gray-dark': '#273444',
        //     'gray': '#8492a6',
        //     'gray-light': '#d3dce6',
        // },
        fontFamily: {
            sans: ['Graphik', 'sans-serif'],
            serif: ['Merriweather', 'serif'],
        },
        extend: {
            spacing: {
                '8xl': '96rem',
                '9xl': '128rem',
            },
            borderRadius: {
                '4xl': '2rem',
            }
        }
    },
    variants: {
        extend: {},
    },
    plugins: [

        // require('@tailwindcss/typography'),
        require('@tailwindcss/forms'),
        // require('@tailwindcss/line-clamp'),
        // require('@tailwindcss/aspect-ratio'),
    ]
}
  ```

  ### Chart Js
  ```
    https://www.chartjs.org/docs/latest/getting-started/installation.html
  ```
  - document link 

    https://www.chartjs.org/docs/latest/charts/doughnut.html#pie

### Font awesome

- link https://fontawesome.com/docs/web/use-with/vue/


```
# Add SVG Core

yarn add @fortawesome/fontawesome-svg-core


# Free icons styles
yarn add @fortawesome/free-solid-svg-icons
yarn add @fortawesome/free-regular-svg-icons
yarn add @fortawesome/free-brands-svg-icons


# for Vue 3.x
yarn add @fortawesome/vue-fontawesome@latest-3

# import to Main Js
import { library } from '@fortawesome/fontawesome-svg-core'

import { faHatWizard } from '@fortawesome/free-solid-svg-icons'

import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'



library.add(faHatWizard)


Vue.component('font-awesome-icon', FontAwesomeIcon)
```

## vuex-persistedstate
this use to  save the Vuex date in local then only posible to get the login values and auth everthing
- ref link (https://yarnpkg.com/package/vuex-persistedstate)

```
yarn add vuex-persistedstate

```

## Crypto Js added for encoding and decoding the file

```
yarn add crypto-js

```


## Email Editor
```
https://github.com/unlayer/react-email-editor/issues/155

https://docs.unlayer.com/docs/custom-file-storage

```

# secure-ls for Encrypt

```
https://classic.yarnpkg.com/en/package/secure-ls
```
