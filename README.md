<div align="center">
  <h1>Strapi v4 - Open Repository for strapi-plugin-translate</h1>
</div>

![repository showcase](https://github.com/The-Easycode/strapi-translation-deepl/blob/master/translation.gif)

Manage and automate the translation of content fields for free. 500000 characters/month in free tier.

## 🚀 Tech Stack

- [strapi](https://www.npmjs.com/package/@strapi/strapi) | Open-source headless CMS
- [@strapi/plugin-i18n](https://www.npmjs.com/package/strapi-plugin-translate) | Strapi v4 - i18n
- [strapi-plugin-translate](https://www.npmjs.com/package/strapi-plugin-translate) | Strapi v4 - Translate plugin
- [strapi-provider-translate-deepl](https://www.npmjs.com/package/strapi-plugin-translate) | Strapi v4 - DeepL provider for Translate Plugin

## 📭 Requirements

- Free DeepL API key, at [deepl](www.deepl.com/pro#developer)
- Duplicate the `.env.example` and rename it to `.env`
- Modify Keys and add your DeepL Key

## ⏳ Installation

```bash
# with npm
$ npm install
# or with yarn
$ yarn
```

After successful installation you have to build a fresh package that includes plugin UI:

```bash
# with npm
$ npm run build && npm run develop
# or with yarn
$ yarn build && yarn develop
```

## ⚙ Configuration

### plugin.js

`config/plugin.js`

```js
module.exports = ({ env }) => ({
  translate: {
    enabled: true,
    config: {
      // Add the name of your provider here (for example 'deepl' for strapi-provider-translate-deepl or the full package name)
      provider: "deepl",
      providerOptions: {
        apiKey: env("DEEPL_API_KEY"),
      },
      // Which field types are translated (default string, text, richtext, components and dynamiczones)
      // Either string or object with type and format
      // Possible formats: plain, markdown, html (default plain)
      translatedFieldTypes: [
        "string",
        { type: "text", format: "plain" },
        { type: "richtext", format: "markdown" },
        "component",
        "dynamiczone",
      ],
      // If relations should be translated (default true)
      translateRelations: true,
    },
  },
});
```

Find more options at [strapi-plugin-translate](https://www.npmjs.com/package/strapi-plugin-translate) and [strapi-provider-translate-deepl](https://www.npmjs.com/package/strapi-plugin-translate).

### app.js

`src/admin/app.js`

- comment out the languages you want to use

```js
  //...
  locales: [
    // 'ar',
    // 'fr',
    // 'cs',
    "de",
    // 'dk',
    // 'es',
    // 'he',
    // 'id',
    // 'it',
    // 'ja',
    // 'ko',
    // 'ms',
    // 'nl',
    // 'no',
    // 'pl',
    // 'pt-BR',
    // 'pt',
    // 'ru',
    // 'sk',
    // 'sv',
    // 'th',
    // 'tr',
    // 'uk',
    // 'vi',
    // 'zh-Hans',
    // 'zh',
  ],
  //...
```
