# Permutation task

This is a side project to test UI/UX from different packages for the students task view of a permutation problem.
Webpack is used to generate bundles of js files that will be then imported by the main project.

## Test environment
Using npm:
```
npm install
npm start
```
Using yarn:
```
yarn install
yarn run start
```

## Type checking with flow
Using npm
```
npm run-script flow
```
Using yarn:
```
yarn run flow
```

## Production build
Using npm:
```
npm install
npm run-script build
```
Using yarn:
```
yarn install
yarn run build
```
This command will create a bundle file inside the plugin static file structure.

## About the code

Sometimes, the same object may be referred by different names. The table containing the distractor elements may be called "Misleading table" or "Distractors". This table is different from the "Candidates list" which contains all the elements shuffled.

This project doesn't follow a standard like reactjs. DOM objects are lazily initialized. Usually there will be a method `get_dom()` to build/get the corresponding DOM object.

## API

The studio populates an object `problem` that is then communicated to the backend via python. 
The structure of this object is the following:

 + `[$PID]`: Problem id. Contains a lists of tables.
    + `[$tableId]`: Table id. `0` is misleading table.
        + `["tableName"]`: String containing table name
        + `["tableColor"]`: String containing table color in hex
        + `["text"]`: List of strings containing each row's text in order
        + `["text_id"]`: List of strings containing each row's text id in order
