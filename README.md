# svelte-lingui – i10n for Svelte

This is a first stab at building a reusable module for internationalization,
localization and translation of Svelte and Sapper apps.

## Installation

```sh
yarn add --dev svelte-lingui @lingui/core@next # or npm i --save-dev svelte-lingui @lingui/core@next
```

## Usage

Wrap your app in a provider:
```jsx
<Provider config={{ ...LinguiConfig }}>
  <App />
</Provider>
```

Use `Text` component for messages:
```jsx
<Text message={'Hello {name}'} props={{ name }} />
```

Or use context to access the `i18n` object from Lingui directly:
```js
const i18n = getContext("i18n");   // returns a store
$i18n._(message, props)
```

Checkout the code inside `/dev` for a full example.

## Development

There is a dev app available inside the `/dev` folder that can be used for
testing and experimenting with the components. To start it simply run:

```sh
yarn dev # or npm run dev
```

## Todo

- [ ] Evaluate other i18n/translation libraries (fluent + fluent-compiler, ttag, etc)
- [ ] Implement language detection/negotiation (client side + sapper middleware)
- [ ] Sapper routing
