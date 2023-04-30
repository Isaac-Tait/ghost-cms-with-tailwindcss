# Ghost Starter Theme

A starter framework for Ghost themes!

`cd` into an empty directory then ran the command `ghost install local` then `cd content/themes` followed by `git clone https://github.com/TryGhost/Starter.git ghost-with-tailwind` then `cd ghost-with-tailwind` and `yarn install`

`npm install -D tailwindcss autoprefixer`

`npx tailwindcss init`

### Update Tailwind Config

```
/** @type {import('tailwindcss').Config} */
export default {
  theme: {
    extend: {},
  },
  plugins: [],
  content: [
    "/*.hbs",
    "./**/*.hbs",
  ]
}
```

### Update CSS

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Update Rollup Config

```
// Update the imports
import tailwindcss from 'tailwindcss';
import autoprefixer from 'autoprefixer';

// Update the postcss config
postcss({
            extract: true,
            plugins: [
                tailwindcss,
                autoprefixer
            ]
}),
```

## To see realtime changes during development, symlink the Starter theme folder to the content/themes folder in your local Ghost install.

`cd` back into the home directory (in my case it was `~/Desktop/Web_Dev/My_Novel`) then run

`ln -s temp/content/themes/ghost-with-tailwind temp/content/themes/ghost-with-tailwind`

`ghost restart`

navigate to localhost:2368/ghost follow the setup screen. After that go to Settings > Design > Change Theme and activate the Tailwind Starter

`ghost stop`

`ghost restart`
