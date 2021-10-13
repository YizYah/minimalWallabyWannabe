# minimalWallabyWannabe
This shows some sort of problem with reading in a file.

The `test/sample.test.ts` file is passing when run directly.  But for some reason, the Wallaby.js Tests OUTPUT shows

```

Cannot find module './data' 
  ​​​​​at Object.<anonymous> ​​​​​​test/sample.test.ts:2​

```

In your documentation at [Troubleshooting](https://wallabyjs.com/docs/intro/troubleshooting.html), you specify that 

>   If you are running tests in node.js and getting a Cannot find module error or other ‘file not found’ type of issues, please make sure that files that you are trying to load are listed in the files list. Wallaby.js uses its own cache, so it has to copy used files there. Note that this does not apply to the node_modules folder, as wallaby.js doesn’t cache it and uses your local version of it. So, no need to list node modules in the files list for your node tests (but it may be required for browser tests if you are using node modules as libs).

But you can see that I added a reference to the file directly in the files list of the `wallaby.js` document:
```
    files: [
      'src/**/*.ts',
      'test/data.ts',
    ],

```