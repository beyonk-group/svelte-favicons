## Favicon Generator

Generates favicons for your application.

## Status

A WIP. Currently not working in Sapper at all due to [this issue](https://github.com/sveltejs/sapper/issues/475).

## Usage

First, generate an icon pack, and unzip it somewhere useful like `images/favicons`

Inside a SvelteJS/Sapper application:

```html
  <svelte:head>
    <Favicons />
  </svelte:head>

  <script>
    import Favicons from '@beyonk/svelte-favicons'

    export default {
      components: {
        Favicons
      }
    }
  </script>
```

Inside any other type of application:

```html
  // Currently untested, YMMV.
  <head>
    <script>
      favicons()
    </script>
  </head>

  <script>
    import favicons from '@beyonk/svelte-favicons'

  </script>
```

## Options

```html
  <svelte:head>
    <Favicons :iconPath :generate />
  </svelte:head>

  <script>
    import Favicons from '@beyonk/svelte-favicons'

    export default {
      components: {
        Favicons
      },

      // The below are the component's defaults.
      data () {
        return {
          iconPath: '/images/favicon',
          generate: {
            apple: ['57', '60', '72', '76', '114', '120', '144', '152', '180'],
            android: ['192'],
            favicon: ['32', '96', '16']
          }
        }
      }
    }
  </script>
```