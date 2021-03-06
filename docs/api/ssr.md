# ApolloSSR

## Usage

See [SSR guide](../guide/ssr.md).

## Methods

### prefetchAll

Prefetches all queued component definitions and returns a promise resolved when all corresponding apollo data is ready.

```js
await ApolloSSR.prefetchAll (apolloProvider, componentDefs, context)
```

`context` is passed as the argument to the `prefetch` options inside the smart queries. It may contain the route and the store.

### getStates

Returns the apollo stores states as JavaScript objects.

```js
const states = ApolloSSR.getStates(apolloProvider, options)
```

`options` defaults to:

```js
{
  // Prefix for the keys of each apollo client state
  exportNamespace: '',
}
```

### exportStates

Returns the apollo stores states as JavaScript code inside a String. This code can be directly injected to the page HTML inside a `<script>` tag.

```js
const js = ApolloSSR.exportStates(apolloProvider, options)
```

`options` defaults to:

```js
{
  // Global variable name
  globalName: '__APOLLO_STATE__',
  // Global object on which the variable is set
  attachTo: 'window',
  // Prefix for the keys of each apollo client state
  exportNamespace: '',
}
```
