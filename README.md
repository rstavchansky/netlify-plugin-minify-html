# Netlify Plugin - Minify HTML

This [plugin](https://www.netlify.com/build/plugins-beta?utm_source=github&utm_medium=plugin-htmlminifier-pnh&utm_campaign=devex) adds the ability to minify the HTML generated by your build.

Note: Many SSGs support this as part of their own process so this might not always be necessary.

This plugin is agnostic to the tool being used to generate the markup, and acts purely on the markup it finds in `.html` files in the publish folder which [Netlify](https://www.netlify.com?utm_source=github&utm_medium=plugin-htmlminifier-pnh&utm_campaign=devex) is preparing to deploy to its CDN following as successful build.

## Installation

To include this plugin in your site deployment:


### 1. Add the plugin as a dependency

```bash

# Add the plugin as a dependency of your build
npm i --s netlify-plugin-minify-html

```


### 2. Add the plugin and its options to your netlify.yaml

You can choose which deploy contexts will include the HTML minification with the `targets` option.

You can use the `minifierOptions` config array to pass option to the minifier. A full list of the [available options](https://www.npmjs.com/package/html-minifier#options-quick-reference) are available from the [html-minfier library](https://www.npmjs.com/package/html-minifier)

```yaml
plugins:
  # Path to plugin. Can be local relative path or reference to node_modules
  - package: netlify-plugin-minify-html
    config:
      # Builds in which deploy contexts will get minified?
      # [production, deploy-preview, branch-deploy]
      targets:
        - production
        - deploy-preview
        - branch-deploy
      minifierOptions:
        - removeComments: false
        - removeEmptyElements: true
```

## 🚨 NOTE - Netlify Plugins are currently in private beta

At this time, this plugin will only be available to those participating in the private beta of [Netlify Plugins](https://www.netlify.com/build/plugins-beta?utm_source=github&utm_medium=plugin-htmlminifier-pnh&utm_campaign=devex).

If you would like [access to the beta](https://www.netlify.com/build/plugins-beta?utm_source=github&utm_medium=plugin-htmlminifier-pnh&utm_campaign=devex), you are very welcome to apply.

