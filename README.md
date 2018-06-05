# SharePoint Framework Unit Test Sample with Jest

WRITE DESCRIPTION

![Web part render](/assets/wp-render.png)

When you run the tests, the result should look like this:

![Test results](/assets/test-results.png)

## Extra dependencies
As this is a test sample for testing React components, I made use of the following extra testing dependencies:
- [Jest](https://facebook.github.io/jest/)
- [enzyme]( http://airbnb.io/enzyme)
- enzyme-adapter-react-15
- react-test-renderer

These dependencies are also specified in the `package.json` file. So, once you run `npm install` they will automatically get downloaded.

## HelloWorld.test.ts file extension change to TSX (JSX templating enabled)
The file extension of the default `HelloWorld.test.ts`, which comes with the SPFx yeoman generator, is changed to TSX so that the JSX templating syntax is available. This change is necessary to mount components with enzyme. Example: `renderedElement = mount(<HelloWorld description={descTxt} />);`.

## Jest config

The config for Jest can be found in the `package.json` file. In order to make Jest work with SPFx dependencies, some extra mappings are required:

```
"moduleNameMapper": {
  "\\.(css|scss)$": "identity-obj-proxy",
  "^resx-strings/en-us.json": "<rootDir>/node_modules/@microsoft/sp-core-library/lib/resx-strings/en-us.json"
}
```

- First line is to support CSS and SASS files
- Second line is to correctly load the resource file when using SPFx dependencies

## How to use it?

- Clone this repo
- Run `npm install`
- Run `npm test`
