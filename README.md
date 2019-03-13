To repro:

```
yarn install
tsc -b . --verbose
tsc -b . --verbose
```

The second invocation of `tsc` should do nothing as the source hasn't changed, but it attempts to rebuild because:

```
Project 'tsconfig.json' is out of date because output file '.build/data.json.map' does not exist
```

`tsc` without `-b` works fine of course.
