<!--
The README.md file is a compiled document. No edits should be made directly to this file.

README.md is created by running `npm run build:docs`.

This file is generated based on a template fetched from
`https://raw.githubusercontent.com/AlaskaAirlines/WC-Generator/master/componentDocs/README.md`
and copied to `./componentDocs/README.md` each time the the docs are compiled.

The following sections are editable by making changes to the following files:

| SECTION                | DESCRIPTION                                       | FILE LOCATION                       |
|------------------------|---------------------------------------------------|-------------------------------------|
| Description            | Description of the component                      | `./docs/partials/description.md`    |
| Use Cases              | Examples for when to use this component           | `./docs/partials/useCases.md`       |
| Additional Information | For use to add any component specific information | `./docs/partials/readmeAddlInfo.md` |
| Component Example Code | HTML sample code of the components use            | `./apiExamples/basic.html`          |
-->

# Nav

`<auro-nav>` is a [HTML custom element](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) for the purpose of showing users a secondary navigation aid that helps them understand the relation between the location of their current page and higher level pages.

## UI development browser support

For the most up to date information on [UI development browser support](https://auro.alaskaair.com/support/browsersSupport)

## Install

[![Build Status](https://img.shields.io/github/actions/workflow/status/AlaskaAirlines/auro-nav/testPublish.yml?style=for-the-badge)](https://github.com/AlaskaAirlines/auro-nav/actions/workflows/testPublish.yml)
[![See it on NPM!](https://img.shields.io/npm/v/@aurodesignsystem/auro-nav?style=for-the-badge&color=orange)](https://www.npmjs.com/package/@aurodesignsystem/auro-nav)
[![License](https://img.shields.io/npm/l/@aurodesignsystem/auro-nav?color=blue&style=for-the-badge)](https://www.apache.org/licenses/LICENSE-2.0)

```shell
$ npm i @aurodesignsystem/auro-nav
```

Installing as a direct, dev or peer dependency is up to the user installing the package. If you are unsure as to what type of dependency you should use, consider reading this [stack overflow](https://stackoverflow.com/questions/18875674/whats-the-difference-between-dependencies-devdependencies-and-peerdependencies) answer.

### Design Token CSS Custom Property dependency

The use of any Auro custom element has a dependency on the [Auro Design Tokens](https://auro.alaskaair.com/getting-started/developers/design-tokens).

### CSS Custom Property fallbacks

[CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) are [not supported](https://auro.alaskaair.com/support/custom-properties) in older browsers. For this, fallback properties are pre-generated and included with the npm.

Any update to the Auro Design Tokens will be immediately reflected with browsers that support CSS custom properties, legacy browsers will require updated components with pre-generated fallback properties.

### Define dependency in project component

Defining the component dependency within each component that is using the `<auro-nav>` component.

```js
import "@aurodesignsystem/auro-nav";
```

**Reference component in HTML**

```html
<auro-nav>
  <auro-breadcrumb href="http://auro.alaskaair.com/components/auro/nav">Home</auro-breadcrumb>
  <auro-breadcrumb href="http://auro.alaskaair.com/components/auro/nav">Level 2</auro-breadcrumb>
  <auro-breadcrumb href="http://auro.alaskaair.com/components/auro/nav">Level 3</auro-breadcrumb>
  <auro-breadcrumb href="http://auro.alaskaair.com/components/auro/nav">Level 4</auro-breadcrumb>
  <auro-breadcrumb>Current</auro-breadcrumb>
</auro-nav>
```

## Install bundled assets from CDN

In cases where the project is not able to process JS assets, there are pre-processed assets available for use. See -- `auro-nav__bundled.js` for modern browsers. Legacy browsers such as IE11 are no longer supported.

We recommend you load these bundles using [differential serving](https://philipwalton.com/articles/deploying-es2015-code-in-production-today/) so that the browser only loads the bundle correctly. To accomplish this, the script tag for the modern bundle should have `type="module"` and the script tag.

### Bundle example code

```html
<!-- **NOTE:** Be sure to replace `@latest` in the URL with the version of the asset you want. @latest is NOT aware of any MAJOR releases, use at your own risk. -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@alaskaairux/design-tokens@latest/dist/tokens/CSSCustomProperties.css" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@aurodesignsystem/webcorestylesheets@latest/dist/bundled/essentials.css" />
<script src="https://cdn.jsdelivr.net/npm/@aurodesignsystem/auro-nav@latest/dist/auro-nav__bundled.js" type="module"></script>
```

## auro-nav use cases

The `<auro-nav>` element acts as a container for a series of links representing a level of depth in the site content. 
The `<auro-nav>` element should only be used for multi-page projects that have 3 to 5 levels of page depth.

## API Code Examples

### Default auro-nav

```html
<auro-nav>
  <auro-breadcrumb href="http://auro.alaskaair.com/components/auro/nav">Home</auro-breadcrumb>
  <auro-breadcrumb href="http://auro.alaskaair.com/components/auro/nav">Level 2</auro-breadcrumb>
  <auro-breadcrumb href="http://auro.alaskaair.com/components/auro/nav">Level 3</auro-breadcrumb>
  <auro-breadcrumb href="http://auro.alaskaair.com/components/auro/nav">Level 4</auro-breadcrumb>
  <auro-breadcrumb>Current</auro-breadcrumb>
</auro-nav>
```

## Development

In order to develop against this project, if you are not part of the core team, you will be required to fork the project prior to submitting a pull request.

Please be sure to review the [contribution guidelines](https://auro.alaskaair.com/contributing) for this project. Please make sure to **pay special attention** to the **conventional commits** section of the document.

### Start development environment

Once the project has been cloned to your local resource and you have installed all the dependencies you will need to open a shell session to run the **dev server**.

```shell
$ npm run dev
```

Open [localhost:8000](http://localhost:8000/)

If running separate sessions is preferred, please run the following commands in individual terminal shells.

```shell
$ npm run build:watch

$ npm run serve
```

### API generation

The custom element API file is generated in the build and committed back to the repo with a version change. If the API doc has changed without a version change, author's are to run `npm run build:api` to generate the doc and commit to version control.

### Testing

Automated tests are required for every Auro component. See `.\test\auro-nav.test.js` for the tests for this component. Run `npm test` to run the tests and check code coverage. Tests must pass and meet a certain coverage threshold to commit. See [the testing documentation](https://auro.alaskaair.com/support/tests) for more details.

### Bundled assets

Bundled assets are only generated in the remote and not merged back to this repo. To review and/or test a bundled asset locally, run `$ npm run bundler` to generate assets.

