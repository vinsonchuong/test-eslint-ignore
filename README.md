# test-eslint-ignore
A minimal example for gathering data on how `eslint` ignores the `node_modules` directory.

```sh
git clone https://github.com/vinsonchuong/test-eslint-ignore
cd test-eslint-ignore
npm install

echo 'debugger;' > node_modules/foo.js

time ./node_modules/.bin/eslint .
time ./node_modules/.bin/eslint index.js
time ./node_modules/.bin/eslint node_modules index.js
```

Notice that running `eslint .` takes as long as running
`eslint node_modules index.js` and that running `eslint index.js` takes much
less time.
