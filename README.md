# Use Imglabs.io to optimize images in your Next.js app

In your `next.config.js` file:

```js
module.exports = {
  images: {
    loader: 'custom',
    loaderFile: './my/image/loader.js',
  },
}
```

In `./my/image/loader.js`:

```js
const id = '00000000-0000-0000-0000-000000000000';
const baseUrl = 'https://example.com';

export default function imglabsLoader({ src, width, quality }) {
  return `https://imglabs.io/?id=${id}&url=${baseUrl}${src}&thumbnail=n,${width},99999`
}
```

Visit the [Imglabs.io documentation](https://www.imglabs.io/docs) on instructions to get your Imglabs.io ID.
