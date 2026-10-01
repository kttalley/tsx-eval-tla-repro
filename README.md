# tsx `-e` top-level await repro

`package.json` has `"type": "module"`.

```sh
npm install
node -e "await Promise.resolve(1); console.log('ok')"                          # ok
npx tsx --input-type=module -e "await Promise.resolve(1); console.log('ok')"  # ok
npx tsx -e "await Promise.resolve(1); console.log('ok')"                      # fails
```

The last command fails with:

```
ERROR: Top-level await is currently not supported with the "cjs" output format
```

See the Actions run for the output.
